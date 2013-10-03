---
layout: post
title: "Getting started with Wordpress in Openshift"
category: 
tags: []
published: false
image: /images/posts/openshift-enterprise.jpg
---
{% include JB/setup %}
Openshift is one of the best cloud platform recently created to make developers live easier, and once you <a href="https://www.openshift.com/products/architecture" target="_blank">understand</a> how it work it really does, but it is also true that we need some time to stay ready to be productive with it.

There are great documentation to deploy wordpress in the "official way" <a href="https://www.openshift.com/quickstarts/wordpress-3x" target="_blank">here</a>, but the idea of this post is to explain how I stated using Openshift, deploying Wordpress instances and how I adapt the defaults instructions for that in order to work with a local environment synchronized with the Openshift instance.

<a href="https://www.openshift.com/" target="_blank"><img src="{{site.production_url}}//images/posts/openshift-enterprise.jpg" /></a>

1. The first thing you need to do is to create a new an Openshift account in <a href="https://www.openshift.com/" target="_blank">www.openshift.com/</a>.

2. Then we need to have installed and configured the <a href="https://www.openshift.com/developers/rhc-client-tools-install" target="_blank">OpenShift Client Tools (rhc)</a>.

3. The third step is to execute the creation command using my forked <a href="https://github.com/robertovg/wordpress-example" target="_blank">wordpress-example</a>. I use it because don't have the worpdress sources ( so we use the last update ) and I prepared some helpful alias in deploy script, so the configuration in the openshift instance will be automatically 

    `rhc app create yourWPName php-5 mysql-5 --from-code=https://github.com/robertovg/wordpress-example`

This will also clone the current gear structure in a folder called like yourWPName.

4. Then we have to download the Wordpress we want and unzip it into &lt;cloneDirectory&gt;/php folder.

. If we add, commit and finally push all files to the server, you will have an instance of the version you have downloaded up and running on the following url: 

    `http://yourWPName-$yournamespace.rhcloud.com`

It is a good idea to configure your Wordpress instance through the web console, do not install any pluging or theme yet.

6. Once we have our openshift wordpress up and running we have to make a backup of it, so we can clone the database, this is useful to have the same configuration, but once cloned we need
