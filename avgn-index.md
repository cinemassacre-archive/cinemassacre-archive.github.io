---
layout: default
title: Index of AVGN Videos
permalink: /avgn-index
---
<div id="top"></div>

<h1 class="center">Angry Video Game Nerd Video Index</h1>
<p class="center">
<a href="#2004">2004</a> | 
<a href="#2006">2006</a> | 
<a href="#2007">2007</a> | 
<a href="#2008">2008</a> | 
<a href="#2009">2009</a> | 
<a href="#2010">2010</a> | 
<a href="#2011">2011</a> | 
<a href="#2012">2012</a> | 
<a href="#2013">2013</a> | 
<a href="#2014">2014</a> | 
<a href="#2015">2015</a> | 
<a href="#2016">2016</a> | 
<a href="#2017">2017</a> | 
<a href="#2018">2018</a> | 
<a href="#2019">2019</a> | 
<a href="#2020">2020</a> | 
<a href="#nes-marathon">NES Marathon mini-episodes</a>|
<a href="#bad-covers">Bad Cover Art</a></p>

I still have some videos to add, but the main stuff is here.

The individual video pages aren't all done yet, but every one has its video included at the very least. I'm still working on adding games, platforms, descriptions, etc.

{% for video in site.avgn %}
{% if video.special %}
{% assign currentSection = video.special_id %}
{% if currentSection != section %}
  {% unless forloop.first %}</table>{% endunless %}
  <h1 id="{{ video.special }}"> {{ currentSection }}</h1>
  <table>
  <tr>
    <th class="index-episode-number">#</th>
    <th class="index-episode-title">Episode Title</th>
    <th class="index-release-date">Release Date</th>
    <th class="index-platforms">Platforms Covered</th>
    <th class="index-games">Games Covered</th>
  </tr>
  {% assign section = currentSection %}
{% endif %}
  <tr>
    <th class="lighter">{% if video.episode %}{{ video.episode }}{% else %}-{% endif %}</th>
    <th class="lighter index-episode-title-rows"><a href="{{ video.url }}">{{ video.title }}</a></th>
    <th class="lighter">{{ video.release_date | date: "%B %-d, %Y" }}</th>
    <th class="lighter">{% if video.short_platforms %}{% for platform in video.short_platforms %}<li>{{ platform }}</li>{% endfor %}{% endif %}</th>
    <th class="lighter">{% if video.games %}{% for game in video.games %}<li>{{ game }}</li>{% endfor %}{% endif %}</th>
  </tr>
{% if forloop.last %}</table>{% endif %}
{% else %}
{% assign currentSection = video.release_date | date: "%Y" %}
{% if currentSection != section %}
  {% unless forloop.first %}</table>{% endunless %}
  <h1 id="{{ currentSection }}"> {{ currentSection }}</h1>
  <table>
  <tr>
    <th class="index-episode-number">#</th>
    <th class="index-episode-title">Episode Title</th>
    <th class="index-release-date">Release Date</th>
    <th class="index-platforms">Platforms Covered</th>
    <th class="index-games">Games Covered</th>
  </tr>
  {% assign section = currentSection %}
{% endif %}
  <tr>
    <th class="lighter">{% if video.episode %}{{ video.episode }}{% else %}-{% endif %}</th>
    <th class="lighter index-episode-title-rows"><a href="{{ video.url }}">{{ video.title }}</a></th>
    <th class="lighter">{{ video.release_date | date: "%B %-d, %Y" }}</th>
    <th class="lighter">{% if video.short_platforms %}{% for platform in video.short_platforms %}<li>{{ platform }}</li>{% endfor %}{% endif %}</th>
    <th class="lighter">{% if video.games %}{% for game in video.games %}<li>{{ game }}</li>{% endfor %}{% endif %}</th>
  </tr>
{% if forloop.last %}</table>{% endif %}
{% endif %}
{% endfor %}