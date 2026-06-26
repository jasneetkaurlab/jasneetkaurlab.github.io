---
layout: page
permalink: /gallery/
title: Gallery
description: Photos from the Sustainable Nano Engineered Materials Lab — research, group activities, and events.
nav: true
nav_order: 6
---

<!-- _pages/gallery.md -->
<!-- To add photos: drop image files into assets/img/gallery/ — they appear here automatically. -->

{% assign gallery_images = site.static_files | where_exp: "f", "f.path contains '/assets/img/gallery/'" | where_exp: "f", "f.extname != '.webp'" %}

{% if gallery_images.size > 0 %}
{% include gallery_grid.liquid %}
{% else %}

<p>No photos yet — check back soon!</p>
{% endif %}
