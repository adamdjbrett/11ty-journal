---
title: Tags
description: Collections of tags
---
<ul>
{% for tag in collections | getKeys | filterTagList %}
	{% set tagUrl %}/tags/{{ tag | slugify }}/{% endset %}
	<li><a href="{{ tagUrl }}" class="post-tag">{{ tag }}</a></li>
{% endfor %}
</ul>
