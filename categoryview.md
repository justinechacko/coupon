---
    layout: page
    title: Post by Category
    permalink: /categoryview/
---
<div>
    {% assign categories = site.categories | sort %}
    {% for category in categories %}
     <span class="site-tag">

        <a href="#{{ category | first | slugify }}"><button class="btn btn-default" type="button">
                {{ category[0] | replace:'-', ' ' }} <span class="badge">{{ category | last | size }}</span></button>
        </a>

    </span>
    {% endfor %}

    </div>
<hr>
<div id="index">
 

 {% for category in categories %}
<h4>
    <a name="{{ category[0] }}"><button class="btn btn-default" type="button">{{ category[0] | replace:'-', ' ' }} <span class="badge"> {{ category | last | size }}</span></button>
        </a>
</h4>
    {% assign sorted_posts = site.posts | sort: 'title' %}
    {% for post in sorted_posts %}
    {%if post.categories contains category[0]%}

      <span style="font-size: 18px;"><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span> &bull; <span class="post-meta">{{ post.date | date: date_format }}</span>
     
 
       <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
 <hr>
    {%endif%}
    {% endfor %}

    {% endfor %}
</div>
