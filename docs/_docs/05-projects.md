---
layout: archive
title: "Projects Catalog"
permalink: /docs/projects/
author_profile: false
---

<div class="grid__wrapper">
  {% for post in site.projects %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>