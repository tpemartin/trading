---
layout: page
title: "Daily Juice"
description: "用一杯果汁，品嘗世界"
permalink: /daily-juice/
---
<!-- <span id="note">{{page.title}}</span> -->
{% for post in site.posts %}
  {% if post.category contains "daily-juice" %}
  {%unless post.tags contains "closed"%}
  <h4 class="post">
  <strong>
  <a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}">{{ post.title | capitalize }}</a>
  </strong>
  <small>{{ post.date | date_to_string }}</small>
  </h4>
  <div class="row">

    <div class="nine columns">
      {{ post.description }}
    </div>

    {% if post.image[0] %}
    <div class="three columns">
      <a target="_blank" href="{{ post.url }}">
        <figure class="thumb">
          <amp-img itemprop="image" src="{{ post.image[0] }}" alt="" layout=""
          width="160px" height="100px">
          </amp-img>
        </figure>
      </a>
    </div>
    {% endif %}



  </div>
  {% endunless %}
  {% endif %}
{% endfor %}
