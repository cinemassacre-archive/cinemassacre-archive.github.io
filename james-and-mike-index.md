---
layout: series-index
title: James and Mike Mondays Episode Index
permalink: /james-and-mike-index
---

<h1 class="center">James and Mike Video Index</h1>

<h2 class="center">Coming Soon</h2>

{% for video in site.james-and-mike %}
{% assign currentSection = video.release_date | date: "%Y" %}
{% if currentSection != section %}
  {% unless forloop.first %}</table>{% endunless %}
  <h1 id="{{ currentSection }}"> {{ currentSection }}</h1>
  <table>
  <tr>
    <th class="index-episode-title">Video Title</th>
    <th class="index-release-date">Release Date</th>
    <th class="index-platforms">Platforms Covered</th>
    <th class="index-games">Games Covered</th>
  </tr>
  {% assign section = currentSection %}
{% endif %}
  <tr>
    <th class="lighter index-episode-title-rows"><a href="{{ video.url }}">{{ video.title }}</a></th>
    <th class="lighter">{{ video.release_date | date: "%B %-d, %Y" }}</th>
    <th class="lighter">{% if video.short_platforms %}{% for platform in video.short_platforms %}<li>{{ platform }}</li>{% endfor %}{% endif %}</th>
    <th class="lighter">{% if video.games %}{% for game in video.games %}<li>{{ game }}</li>{% endfor %}{% endif %}</th>
  </tr>
{% if forloop.last %}</table>{% endif %}
{% endfor %}