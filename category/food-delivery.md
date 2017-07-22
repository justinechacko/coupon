---
layout: page
title: Food Delivery
permalink: /category/food-delivery/
---
<div>



  {% for post in site.categories.food-delivery %}
    {% if post.url %}
{% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
        <span style="font-size: 18px;"><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span> &bull; <span class="post-meta">{{ post.date | date: date_format }}</span>
     
  <hr>

    {% endif %}
  {% endfor %}


</div>
