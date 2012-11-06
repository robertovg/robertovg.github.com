---
layout: page
title: Welcome!
tagline: Supporting tagline
---
{% include JB/setup %}



<div>
	<ul>
  	{% for post in site.posts %}
	    <li>
	    	<article>
		    	<span>{{ post.date | date_to_string }}</span> &raquo; <h3><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h3>
		    	{{ post.description | truncate: 500 }}
	    	</article>
	    </li>	    
  	{% endfor %}
	</ul>
</div>

