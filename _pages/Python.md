---
layout: archive
permalink: /ML/
title: Python + ML / DL
date: {{ date }}
modified:
excerpt:
image:
  feature:
  teaser:
  thumb:
ads: false  
---
{% for post in site.posts %}
	{% unless post.categories contains 'ML' %}
		{% continue %}
	{% endunless %}
  <article>
    {% if post.link %}
      <h2 class="link-post"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a> <a href="{{ post.link }}" target="_blank" title="{{ post.title }}"><i class="fa fa-link"></i></a></h2>
    {% else %}
      <h2><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
    {% endif %}
  </article>
{% endfor %}