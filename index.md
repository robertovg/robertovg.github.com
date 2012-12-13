---
layout: page
title: Index
group: navigation
---
{% include JB/setup %}

<h2>Latest Posts</h2>

{% for post in site.posts %}
<div class="post">
	<h3><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a><span class="date">{{ post.date | date_to_string }}</span></h3>
	{% if post.image %}<a href="{{ BASE_PATH }}{{ post.url }}"><img src="{{ post.image }}" /></a>{% endif %}
	{{ post.content | strip_html | truncatewords: 250 | textilize }}

	<div class="more">
		<a href="{{ BASE_PATH }}{{ post.url }}" class="btn">read more..</a>
	</div>
</div>
<hr/>
{% endfor %}