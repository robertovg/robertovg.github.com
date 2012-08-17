---
layout: page
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}



<div>
  {% for post in site.posts %}
    <article>
	    <li>
	    	<span>{{ post.date | date_to_string }}</span> &raquo; <h3><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h3>
	    	{{ post.description | truncate: 500 }}
	    </li>
    
    </article>


  {% endfor %}
</div>

