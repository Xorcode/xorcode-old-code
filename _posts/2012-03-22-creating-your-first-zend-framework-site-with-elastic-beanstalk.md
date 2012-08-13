---
layout: post
status: publish
published: true
title: Creating your first Zend Framework site with Elastic Beanstalk
author: Torgny Bjers
author_login: tbjers
author_email: tbjers@xorcode.com
author_url: http://xorcode.com/
excerpt: ! "Trying out the new feature of AWS Elastic Beanstalk we created and deployed
  a Zend Framework PHP project to Elastic Beanstalk in less than five minutes using
  git.\r\n"
wordpress_id: 502
wordpress_url: http://xorcode.com/?p=502
date: 2012-03-22 19:22:04.000000000 -04:00
categories:
- Guides
tags:
- amazon
- php
- aws
- elastic beanstalk
---

{% include JB/setup %}

Trying out the new feature of AWS Elastic Beanstalk we created and deployed a Zend Framework PHP project to Elastic Beanstalk in less than five minutes using git.
<a id="more"></a><a id="more-502"></a>
<img class=" wp-image-521 alignright" title="Elastic Beanstalk" src="http://xorcode.com/assets/2012/03/beanstalk.png" alt="" width="124" height="124" />We decided to try with a clean copy of Zend Framework to determine what we had to do to get one of our PHP Zend Framework powered sites up and running successfully on <a href="http://aws.amazon.com/elasticbeanstalk/">Elastic Beanstalk</a>. Using the Zend Studio project creation wizard we set up HelloWorld.

HelloWorld ran fine after we downloaded <a href="http://framework.zend.com/">Zend Framework</a> and placed it in <code>library/</code> and added it to the <code>autoloaderNamespaces</code> configuration parameter. A few minor changes to the configuration of the Elastic Beanstalk environment are necessary to ensure that Zend Framework runs as it should.

<a href="http://xorcode.com/assets/2012/03/AWS-Management-Console.png"><img class="alignnone  wp-image-513" title="AWS Management Console" src="http://xorcode.com/assets/2012/03/AWS-Management-Console.png" alt="" width="605" height="484" /></a>

Note that we used the Document Root <code>/public</code> to indicate that the web server container should be using the standard Zend Framework public directory as its starting point. Once this was done and the instances had reloaded their configuration our Zend Framework site popped right up and greeted us with the familiar Zend Framework boiler template starting page.

<a href="http://xorcode.com/assets/2012/03/helloworldelasticbeanstalk.png"><img class="alignnone size-full wp-image-515" title="helloworldelasticbeanstalk" src="http://xorcode.com/assets/2012/03/helloworldelasticbeanstalk.png" alt="" width="609" height="408" /></a>

Now you are free to deploy your Zend Framework projects into the cloud with Elastic Beanstalk and PHP. We are excited about this new feature of AWS and we intend to use it to its fullest. We will come back with more updates regarding Amazon and Elastic Beanstalk in the near future.
