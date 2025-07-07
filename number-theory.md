---
layout: page
title: Number Theory
permalink: /number-theory/
---

<ul class="post-list">
{% for post in site.posts %}
	{% if post.tags contains 'number-theory' %}
		<li>
			<span>{{ post.date | date_to_string }}</span>
			<h3>
				<a href="{{post.url}}">{{ post.title }}</a>
			</h3>
		</li>
	{% endif %}
{% endfor %}
</ul>
