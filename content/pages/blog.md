---
layout: "base.njk"
title: Blog
description: "Update from my blog posts"
pagination:
  data: collections.posts
  size: 6
  reverse: true
testdata:
 - item1
 - item2
 - item3
 - item4
permalink: "blog/{% if pagination.pageNumber > 0 %}page-{{ pagination.pageNumber + 1 }}/{% endif %}index.html"
---
<main><heading-anchor>
<div class="w-100 overflow-hidden position-relative" id="top">
<div class="container py-vh-5">
<div class="row d-flex justify-content-center text-center">
<div class="col-12 col-lg-10">
<h1 class="display-huge mb-3">{{title}}</h1>
</div>
</div>
</div>
</div>
<div class="container">
<div class="row d-flex justify-content-center">
<div class="col-11 col-lg-10 col-xl-6">
<div class="row border-bottom">
{%- for item in pagination.items %}
<article class="col-12 border-top px-0 py-4 d-flex justify-content-between align-items-center">
<h2 class="h4 lh-1 mb-0"><a class='text-decoration-none' href="{{item.url}}">{{ item.data.title }}</a></h2>
<time datetime="{{ page.date | htmlDateString }}">{{ page.date | readableDate }}</time>
</article>
{% endfor -%}
</div>
</div>
</div>
</div>
</main>

<div class="container d-flex justify-content-between">
{% if pagination.href.previous %}<div class="col border-top border-end py-vh-3 d-flex align-items-center">
<svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-arrow-left" viewBox="0 0 16 16">
<path fill-rule="evenodd" d="M15 8a.5.5 0 0 0-.5-.5H2.707l3.147-3.146a.5.5 0 1 0-.708-.708l-4 4a.5.5 0 0 0 0 .708l4 4a.5.5 0 0 0 .708-.708L2.707 8.5H14.5A.5.5 0 0 0 15 8z"/></svg>
<a class='ms-2 display-6'  href="{{ pagination.href.previous }}"> Previous</a>
</div>{% endif %}
{% if pagination.href.next %}<div class="col border-top text-end py-vh-3 d-flex align-items-center justify-content-end">
<a class='me-2 display-6'href="{{ pagination.href.next }}">Next <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" class="bi bi-arrow-right" viewBox="0 0 16 16">
  <path fill-rule="evenodd" d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"/>
</svg></a>
</div>{% endif %}
</div>
