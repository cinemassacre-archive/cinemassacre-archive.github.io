---
layout: gallery
permalink: /avgn-title-cards
---

<h1 class="center">AVGN Title Card Gallery</h1>

<div class="gallery">

{% for episode in site.avgn %}
  {% if episode.title-cards != null %}
    {% for title-card in episode.title-cards %}
      <div class="tile">
        <a href="/assets/images/avgn/title-cards/{{ title-card }}" data-caption="Episode {{ episode.episode }}: {{ episode.title }}">
          <img src="/assets/images/avgn/title-cards/{{ title-card }}">
        </a>
        <div class="desc">Episode {{ episode.episode }}: <a href="/avgn/episode-{{ episode.episode }}">{{ episode.title }}</a></div>
      </div>
    {% endfor %}
  {% endif %}
{% endfor %}
</div>