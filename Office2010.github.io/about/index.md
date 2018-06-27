---
layout: archive
permalink: /about/
title: "Latest Posts in *about*"
excerpt: "I make living from IT"
---

<div class="tiles">
{% for post in site.categories.about %}
	{% if post.categories contains 'about' %}
		{% include post-grid.html %}
	{% endif %}
{% endfor %}
</div><!-- /.tiles -->
