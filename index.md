---
layout: page
title: Home
---
{% include JB/setup %}

<h2>Latest Posts</h2>

{% for post in site.posts %}
<div class="post">
	<h3><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a><span class="date">{{ post.date | date_to_string }}</span></h3>
	{{ post.content | split:"<img" | last | split:"/>" | first | prepend:"<img" | append:"/>" }} 
	{{ post.content | strip_html | truncatewords: 200 | textilize }}

	<div class="more">
		<a href="{{ BASE_PATH }}{{ post.url }}" class="btn">read more..</a>
	</div>
</div>
<hr/>
{% endfor %}