---
    layout: page
    title: Post by Store
    permalink: /storeview/
---
<div>
      {% assign tags = site.tags | sort %}
      {% for tag in tags %}
        <span class="site-tag">
          <a href="#{{ tag | first | slugify }}"><button class="btn btn-default" type="button">
                {{ tag[0] | replace:'-', ' ' }} <span class="badge">{{ tag | last | size }}</span></button>
          </a>
        </span>
      {% endfor %}
</div>
<hr>
<div id="index">
  {% for tag in tags %}
    <h4>
    <a name="{{ tag[0] }}"><button class="btn btn-default" type="button">{{ tag[0] | replace:'-', ' ' }} <span class="badge"> {{ tag | last | size }}</span></button>
        </a>
</h4>
    {% assign sorted_posts = site.posts | sort: 'title' %}
    {% for post in sorted_posts %}
    {%if post.tags contains tag[0]%}

      <span style="font-size: 18px;"><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span> &bull; <span class="post-meta">{{ post.date | date: date_format }}</span>


       <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
 <hr>
    {%endif%}
    {% endfor %}

    {% endfor %}
</div>
