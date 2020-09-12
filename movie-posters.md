---
layout: gallery
permalink: /movie-posters
title: Movie Poster Gallery
---

<h1 class="center">Cinemassacre Poster Gallery</h1>

<p>This page will populate as video pages are completed. A few aren't in here yet.</p>

<div class="gallery">

{% for video in site.other-videos %}
  {% if video.poster != null %}
    {% for poster in video.poster %}
      <div class="tile" style="width: 24%; height: 36%;">
        <a href="/assets/images/posters/{{ poster }}" data-caption="{{ video.title }}">
          <img src="/assets/images/posters/{{ poster }}">
        </a>
        <div class="desc" style="height: 50px;"><a href="{{ video.url }}">{{ video.title }}</a></div>
      </div>
    {% endfor %}
  {% endif %}
{% endfor %}
</div>