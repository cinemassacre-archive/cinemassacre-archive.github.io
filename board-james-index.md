---
layout: series-index
title: Board James Episode Index
permalink: /board-james-index
---
<h1 class="center">Board James Video Index</h1>

{% for video in site.board-james %}
{% if video.series == "Board James Extras" %}
{% assign currentSection = video.series %}
{% if currentSection != section %}
  {% unless forloop.first %}</table>{% endunless %}
  <h1 id="{{ video.special }}"> {{ currentSection }}</h1>
  <table>
  <tr>
    <th class="index-episode-number">#</th>
    <th class="index-episode-title">Title</th>
    <th class="index-release-date">Release Date</th>
    <th class="index-games">Games Covered</th>
  </tr>
  {% assign section = currentSection %}
{% endif %}
  <tr>
    <th class="lighter">{% if video.episode %}{{ video.episode }}{% else %}-{% endif %}</th>
    <th class="lighter index-episode-title-rows"><a href="{{ video.url }}">{{ video.title }}</a></th>
    <th class="lighter">{{ video.release_date | date: "%B %-d, %Y" }}</th>
    <th class="lighter">{% if video.games %}{% for game in video.games %}<li>{{ game }}</li>{% endfor %}{% endif %}</th>
  </tr>
{% if forloop.last %}</table>{% endif %}
{% else %}
{% assign currentSection = video.season %}
{% if currentSection != section %}
  {% unless forloop.first %}</table>{% endunless %}
  <h1 id="season-{{ currentSection }}">Season {{ currentSection }}</h1>
  <table>
  <tr>
    <th class="index-episode-number">#</th>
    <th class="index-episode-title">Title</th>
    <th class="index-release-date">Release Date</th>
    <th class="index-games">Games Covered</th>
  </tr>
  {% assign section = currentSection %}
{% endif %}
  <tr>
    <th class="lighter">{% if video.episode %}{{ video.episode }}{% else %}-{% endif %}</th>
    <th class="lighter index-episode-title-rows"><a href="{{ video.url }}">{{ video.title }}</a></th>
    <th class="lighter">{{ video.release_date | date: "%B %-d, %Y" }}</th>
    <th class="lighter">{% if video.games %}{% for game in video.games %}<li>{{ game }}</li>{% endfor %}{% endif %}</th>
  </tr>
{% if forloop.last %}</table>{% endif %}
{% endif %}
{% endfor %}