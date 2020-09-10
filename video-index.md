---
layout: default
permalink: video-index
---

<h1 class="center">Cinemassacre Video Index</h1>
<p class="center">
<a href="#1989">1989</a> | 
<a href="#1991">1991</a> | 
<a href="#1992">1992</a> | 
<a href="#1993">1993</a> | 
<a href="#1994">1994</a> | 
<a href="#1996">1996</a></p>

{% for video in site.other-videos %}
{% assign currentSection = video.release_date | date: "%Y" %}
{% if currentSection != section %}
  {% unless forloop.first %}</ul>{% endunless %}
  <h1 id="{{ currentSection }}"> {{ currentSection }}</h1>
  <ul>
  {% assign section = currentSection %}
{% endif %}
  <li>
    <h2><a href="{{ video.url }}">{{ video.title }}</a></h2>
    {% if video.video_available == false %}
      <p><em>No video available.</em></p>
    {% endif %}
    <p>{{ video.old_cm_description }}</p>
  </li>
{% if forloop.last %}</ul>{% endif %}
{% endfor %}