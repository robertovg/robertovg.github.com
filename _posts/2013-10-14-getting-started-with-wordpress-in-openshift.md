---
layout: post
title: "Getting started with Wordpress in Openshift"
category: hosting
tags: [openshift, dscm, git, javaScript redhat, wordpress ]
published: true 
image: /images/posts/openshift-enterprise.jpg
---
{% include JB/setup %}
<a href="https://www.openshift.com/" target="_blank"><img src="{{site.production_url}}//images/posts/openshift-enterprise.jpg" /></a>
First of all I would like to say that I don't use to write technical tutorials or guides but there's always a first time, isn't there?. Anyway this will be more some brief steps to follow more than a technical tutorial indeed but I hope it's useful in order to start using Openshift as your <a href="http://en.wikipedia.org/wiki/Platform_as_a_service" target="_blank">PaaS</a>.

Openshift is one of the best cloud platform recently created to make developers life easier, and once you <a href="https://www.openshift.com/products/architecture" target="_blank">understand</a> how it work it and how to use it it will become a great place where deploy your projects. Otherwise it is also true that some time is needed to get ready to be productive with it. I like it because I think you have enough flexibility ( more than most of cloud PaaS available ) but it gives you a lot of work solved, without considering that there is <a href="https://www.openshift.com/products/online" target="_blank">OpenShift Online</a> account that it's for free.

There is a great documentation in the official Openshift webpage and a huge community which would help you with any issue you find. For instance to deploy wordpress in the  "official way" you can find their <a href="https://www.openshift.com/quickstarts/wordpress-3x" target="_blank">documentation</a>, but the idea of this post is to explain how I stated using Openshift, deploying Wordpress instances and how I adapt the defaults instructions to work with a local environment synchronized with the Openshift instance.

## Prerequisites

1. The first thing you need to do it's to **create a new an Openshift account** in <a href="https://www.openshift.com/" target="_blank">www.openshift.com/</a>. 

2. Then you need to have **installed the <a href="https://www.openshift.com/developers/rhc-client-tools-install" target="_blank">OpenShift Client Tools (rhc)</a>**. You will previously need to have installed git and ruby to execute rhc, but the instructions below will also help with that.

3. To **configure your local rhc** installation Openshift provides an easy to use command to generate all the configuration. The configuration will be stored in `~/.openshift/express.conf` file. The command to start with the wizard configuration is: `$rhc setup`.

## Deploy in OpenShift

1. Once we have our environment ready to connect to Openshift, the next step is to execute the creation command using my forked <a href="https://github.com/robertovg/wordpress-example" target="_blank">wordpress-example</a>. I created it because I changed some little things in my way such as deleted the worpdress sources ( so we use the last update in our installation directly instead of the old one in the official Openshift wordpres-example ) and I prepared some helpful alias in the deploy script ( so the configuration in the Openshift instance will be automatic and won't conflict with the local configuration, even using the same sources ). The following command will also **clone the current gear structure in a folder** called like 'yourWPName' ( of course you can change to the name you want for your wordpress installation ). `$rhc app create 'yourWPName' php-5 mysql-5 --from-code=https://github.com/robertovg/wordpress-example`. The wizard will ask you about 'yournamespace' ( the name-space where all your gears will be allocated ).

2. Then we have to **download the Wordpress sources** we want and unzip it into &lt;cloneDirectory&gt;/php folder. It's important to remember where is our &lt;cloneDirectory&gt; because we will use it again in the followings steps.

3. Afterwards we **add, commit and finally push all files to the git repository**, so you will have an instance of the wordpress version you have downloaded up and running in the following url: `http://yourWPName-$yournamespace.rhcloud.com`.

4. It is a good idea to **configure your Wordpress instance** through the web console (wp-config), do not install any pluging or theme yet. And with that you will have your Wordpress instance installed and running in Openshift.

## Sync your local environment with Openshift

1. First we need **to have installed an Apache server compatible with PHP plus a MySQL database** . You can do it in the way you prefer but I recommend you using <a href="http://www.mamp.info/en/index.html" target="_blank">MAMP</a>, <a href="http://www.apachefriends.org/en/xampp.html" target="_blank">XAMPP</a>, <a href="http://bitnami.com/" target="_blank">bitnami</a> or a tool like these ones.

2. We need **to make a backup of our Openshift Wordpress Gear** ( it's highly recommended to do it each time to keep your data secure ), so we can generate the same instance in our machine cloning the database, this is useful to have exactly the same configuration. So we execute this command `$rhc snapshot save yourWPName`, and in the current directory it will generate a 'tar.gz' file, once we unzip it we will find a 'app-root/data/mysql_dump_snapshot.gz' inside, now we need to connect to our local mysql and execute the script to have the same database as in Openshift instance. 'app-root/data' will also contain all uploaded data to the Openshift server ( gallery, plugins, themes, uploads).

3. Then we need **to configure our Apache** to point to our &lt;cloneDirectory&gt;/php. We can do it in very different ways but I recommend to use alias in the httpd.conf Apache config file. First we need to know we have enabled 'alias_module' at the beginning of the file. Then we need to add the following code in the `<IfModule alias_module>` section or alias.conf file, if exists.

    `Alias /yourWPName "<cloneDirectory>/php"` <br> 
    `<Directory "<cloneDirectory>/php">` <br> 
    `    Options Indexes MultiViews +FollowSymLinks` <br> 
    `    AllowOverride All ` <br> 
    `    Order allow,deny` <br> 
    `    Allow from all` <br> 
    `</Directory>` <br> 

4. The next thing is **configure <a href="https://github.com/robertovg/wordpress-example/blob/master/php/.htaccess-alias" target="_blank">`.htaccess-alias`</a> and <a href="https://github.com/robertovg/wordpress-example/blob/master/php/wp-config-local.php" target="_blank">`wp-config-local.conf`</a>**. These files can be found in the &lt;cloneDirectory&gt;/php. The first one indicate the configuration of the alias for our local Wordpress instance so we will need to change the 'alias' to 'yourWPName' or to the name of your local instance. The second file is the <a href="http://codex.wordpress.org/Editing_wp-config.php" target="_blank">Wordpress configuration file</a>, you will need to configure the database information to make the just restored MySQL accessible.

5. When we have these two files with the correct configuration, then we will need to **create two alias**. So that we move to the &lt;cloneDirectory&gt;/php with the terminal and then we write:

    `$ln -sf .htaccess-alias .htaccess`<br>
    `$ln -sf wp-config-local.conf wp-config.conf`<br>

6. The next thing to do is **to change the 'siteurl' and 'home' rows in the 'wp_options' table** of MySQL. This is important because, otherwise we won't be able to access to the server. So there will appear `http://yourWPName-$yournamespace.rhcloud.com` or something similar, and we have to change it to `http://localhost/yourWPName`.

7. The next step is **to start or restart your Apache server** tool and start using our Wordpress locally.

8. Finally you will be able **to change themes, install plugins and so**. All this changes first in the local environment and then add, commit and push new or updated files to the server. In this way your changes will be automatically deployed into the production ( Openshift ) environment and everything will be first checked locally and changes stored in the git repository. It's important to know that pages, post and this kind of information have to be pushed to the server with the MySQL script. So just to clear the information, **plugin and themes changes from local to server and post ( through git )**, **pages and BD changes from Openshift instance to local ( through backups step 4 )**.


So more or less this is a brief resume how I'm using Openshift to play with Wordpress instances.

