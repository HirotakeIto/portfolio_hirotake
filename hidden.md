---
layout: default
is_contact: true
---

# Memo
<!-- 
参考
http://adragoona.hatenablog.com/entry/2017/02/08/234416 
https://shopify.github.io/liquid/filters/uniq/
-->
自分用のメモ置き場。
{% assign tags = "" | split: "|" %}
{% for blog in site.blogs %}
  {% assign tags = tags | push: blog.tags  %}
{% endfor %}
<!-- {{tags | uniq | join: ", " }} -->
{% assign tags = tags | uniq%}
{% for tag in tags %}
  <h4>{{tag}}</h4>
  {% for blog in site.blogs %}
    {% if blog.tags contains tag %}
<span>&emsp;&emsp;</span><span>{{ blog.date_post }}</span><span>&emsp;</span><a href="{{ blog.url }}">{{ blog.title }}</a>
    {% endif %}
  {% endfor %}
{% endfor %}
