---
layout: page
title: Chip Gallery
permalink: /projects/
nav: true
nav_order: 3
gallery:
  - image: /assets/img/12.jpg
    title: Sample image
    alt: Placeholder photograph for the chip gallery
---

<style>
  .chip-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(min(100%, 260px), 1fr));
    gap: 24px;
    margin: 24px 0 48px;
  }
  .chip-gallery-item {
    margin: 0;
    min-width: 0;
  }
  .chip-gallery-item img {
    display: block;
    width: 100%;
    aspect-ratio: 4 / 3;
    object-fit: contain;
    background: var(--global-card-bg-color, #fff);
    border: 1px solid var(--global-divider-color, #e5e7eb);
    border-radius: 5px;
  }
  .chip-gallery-item figcaption {
    margin-top: 10px;
    font-size: 14px;
    font-weight: 500;
    text-align: center;
    color: var(--global-text-color-light, #64748b);
  }
</style>

<div class="chip-gallery">
  {% for chip in page.gallery %}
    <figure class="chip-gallery-item">
      <img src="{{ chip.image | relative_url }}" alt="{{ chip.alt | default: chip.title | escape }}" loading="lazy">
      {% if chip.title %}<figcaption>{{ chip.title | escape }}</figcaption>{% endif %}
    </figure>
  {% endfor %}
</div>
