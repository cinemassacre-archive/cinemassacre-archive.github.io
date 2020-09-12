---
layout: default
permalink: /blog
title: Old News Posts from Cinemassacre.com
---

<h1 class="center">Old News Posts from Cinemassacre.com</h1>

<h3 class="center">This page is a total work in progress. It will look better later (and be split up so that it's not all loading at once).</h3>

<p>What's here now is basically just a first pass to collect what was available. Some images are noted as missing because they weren't included in the Wayback Machine's archive, but I've found many of them still live in different places on the current Cinemassacre site. The same with embeds - most of those videos are still available. I just need to go back through and insert them. It's all a whole process of finding and sorting and all that.</p>

---

{% for blog in site.old-news %}
  <div class="blog-bg">
    {{ blog.content }}
  </div>
{% endfor %}