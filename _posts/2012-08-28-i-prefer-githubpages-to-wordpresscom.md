---
layout: post
title: "I prefer github:pages to wordpress.com"
category: hosting 
tags: [github, dscm, jekyll, bootstrap, liquid, git, javaScript ]
published: true
image: /images/posts/scrcap-theme.png
---
{% include JB/setup %}
<p>This is the first article a write entirely in English and the first one I do in this platform with Jekyll, and I have to admit that I find it much more familiar than I expected, because it's such as write code documentation, and it makes me comfortable. Of course I know this article will have some spelling mistakes, but I really think the best way to learn English is to practice it, so ... here we are.</p>
<img title="GitHub:Pages" src="{{ site.production_url }}/images/posts/scrcap-theme.png" alt="GitHub:Pages"   />

<p>In this article I would like to explain why I have changed my personal blog to github. Here goes the reasons:</p>
<p>
	<ul>
		<li>
			One of the main reasons is that with <strong>github:pages you have always the control</strong>. Github:pages allow me to change all documents html, css or js directly ( back to the roots ), I can redirect this page to my custom url domain name, or even I can make little js experiments without worry about the price I have to pay to do these things in your own blog. 
		</li>
		<li>
			The second reason is that is that it is <strong>simplest way of publish static content</strong>. I think most of websites of the Internet don't need to be in a dynamic server ( php, ruby, python, java or whatever your server language is). They just do what the most of web does, but if you only show content, why to use a CMS or something like that?. There are a lot of disadvantage, CMS are a more complicated way to publish, you need a database, the server side and to install the same things you have in production in your pc / mac to view what are you publishing before doing. And these are futures problems.
		</li>
		<li>
		  	<strong>Static for the web is not as bad as it seems to be </strong>, if you don't need it. Ok, the problem of organizing and maintaining a big website with only statics files is there, but there are a little trick, just use a little of ruby to transform your organized files in a fully functional static web with <a href="http://jekyllrb.com" target="_blank">jekyll</a> . You even have available template engine with <a href="http://liquidmarkup.org" target="_blank">liquid</a> and <a href="http://yaml.org" target="_blank">Yalm</a> to specifies properties of each post, and in that way it possible.
		</li>
		<li>
			<strong>This hosting it's free</strong>, and when I say free I mean in deep meaning ( without advertises as does happen in wordpress ) so <a href="http://pages.github.com/" taget="_blankw">github:pages</a> is there to make developer life easier. There are such options as ruby + git hostings exists, for example; <a href="http://www.heroku.com" target="_blank">heroku</a>, but they are not completely free.
		</li>
		<li>
			<strong><a href="http://en.wikipedia.org/wiki/Dynamic_HTML" target="_blank">dhtml</a> rocks!</strong> Well... this is my favorite argument, yes with javaScript you can do everything you are used to do in the server side running javaScript code in each client adding content in pages "dynamically". For example the comments in this blog exists because of <a href="http://disqus.com/" target="_blank">disqus</a> service witch inject comments functionality after each article content by running a piece of code. And comments are only the beginning you can really do a Rich Internet Application without a dynamic server ( using other services that do have...).
		</li>
		<li>
			<strong>Jekyll is more accessible than it looks</strong>, if you are not developer but want to use this way of blogging there are easy to use "frameworks" / "engines" that allow you to make a blog without coding knowledge; <a href="http://octopress.org" target="_blank">Octopress</a>, <a href="http://jekyllbootstrap.com" target="_blank">Jekyll Bootstrap</a> or the own github:pages <a href="https://help.github.com/articles/creating-pages-with-the-automatic-generator" target="_blank">automatic generator</a>, will help you to start.
		</li>
	</ul>
</p>
<p>So, is this information new to you? Do you agree or disagree with the possibility of doing a blog or a web page with jekyll instead of whatever CMS?</p>
