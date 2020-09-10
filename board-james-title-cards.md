---
layout: gallery
title: Board James Title Card Gallery
permalink: /board-james/title-cards
---
<h1 class="center">Board James Title Card Gallery</h1>

<div class="gallery">

{% for episode in site.board-james %}
  {% if episode.title-cards != null %}
    {% for title-card in episode.title-cards %}
      <div class="tile">
        <a href="/assets/images/board-james/title-cards/{{ title-card }}" data-caption="Episode {{ episode.episode }}: {{ episode.title }}">
          <img src="/assets/images/board-james/title-cards/{{ title-card }}">
        </a>
        <div class="desc">Episode {{ episode.episode }}: <a href="/board-james/episode-{{ episode.episode }}">{{ episode.title }}</a></div>
      </div>
    {% endfor %}
  {% endif %}
{% endfor %}
</div>