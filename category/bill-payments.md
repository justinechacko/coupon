---
layout: page
title: Bill Payments
permalink: /category/bill-payments/
---
<div>



  {% for post in paginator.categories.bill-payments %}
    {% if post.url %}
{% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
        <span style="font-size: 18px;"><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span> &bull; <span class="post-meta">{{ post.date | date: date_format }}</span>
     
  <hr>

    {% endif %}
  {% endfor %}
<nav aria-label="Page navigation">
{% if paginator.total_pages > 1 %}
  <ul class="pagination">
{% if paginator.previous_page %}
    <li class="page-item">
      <a class="page-link" href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}" tabindex="-1">&laquo; Previous</a>
    </li>
{% else %}
<li class="page-item disabled">
      <a class="page-link" href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}" tabindex="-1">&laquo; Previous</a>
    </li>
{% endif %}

   {% if paginator.next_page %}
    <li class="page-item"><a class="page-link" href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a></li>
  {% else %}
    <li class="page-item disabled"><a class="page-link" href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Next &raquo;</a></li>
  {% endif %}
  </ul>
{% endif %}
</nav> 

</div>
