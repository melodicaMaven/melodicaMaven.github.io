---
title: Gallery
layout: default
permalink: /gallery/
---

<h2>Yellowstone</h2>
<hr>
<div class="gallery">

{% assign media = site.static_files | where_exp: "file", "file.path contains 'assets/images/2026-yellowstone/fullimgs'" %}

{% for item in media %}

  {% assign ext = item.extname | downcase %}

  {% if ext == '.jpg' or ext == '.jpeg' or ext == '.png' or ext == '.webp' %}

    <a href="{{ item.path | relative_url }}"
       data-lightbox="yellowstone">

		<img src="{{ item.path | replace: 'full/', 'thumbs/' | relative_url }}"
			loading="lazy"
			alt="">
    </a>

  {% elsif ext == '.mp4' %}

    <video controls preload="metadata">
      <source src="{{ item.path | relative_url }}" type="video/mp4">
    </video>

  {% endif %}

{% endfor %}

</div>