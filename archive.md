---
layout: page
title: "Archive"
description: "文章归档，所有文章按发布时间排序，若要根据标签排序，请转到`Tags`"
header-img: "img/orange.jpg"
---

<a href="https://github.com/OldTomatooo">
    <img border="0" src="https://s3.ax1x.com/2021/02/27/69CUBT.png" />
</a>

<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator">{{ y }}</li>
  {% endif %}
  <li class="listing-item">
    <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
