---
layout: home
title: Xorcode
---
{% include JB/setup %}

<div class="hero-unit">
<h1>You started using tools 800,000 years ago</h1>
<h2>Welcome to the evolution of your toolbox</h2>
<p>Much as our early ancestors used tools to bag their prey; we help you bag customers, and keep them. Xorcode delivers scalable web solutions such as integrated billing systems, content management systems, development tools, as well as plugins and complete customizations for WordPress, Drupal, and other CMS software.</p>
<!-- <p>Xorcode takes pride in its experience developing applications for PHP, Perl, and Android. We have written integrated billing systems for the hosting industry, content management systems, PHP development tools, and a multitude of plugins and templates for WordPress and other CMS software.</p> -->
<p><a class="btn btn-primary btn-large" href="about.html">Learn more &raquo;</a></p>
</div>

<div class="row">
<div class="span4">
<h2>Recent Articles</h2>
<ul class="nav nav-pills nav-stacked">
{% for post in site.posts limit:6 %}
  <li><span><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></span></li>
{% endfor %}
</ul>
</div>
<div class="span8">
<h2>Featured Applications</h2>
</div>
</div>
