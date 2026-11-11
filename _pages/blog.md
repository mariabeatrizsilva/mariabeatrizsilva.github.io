---
title:  "Blog"
layout: archive
permalink: /blog/
author_profile: true
comments: true
classes: wide
---

{% for post in site.posts%}
    {% include archive-single.html %}
{% endfor %}

<style>
  .page__title { margin-bottom: 0.5rem; }
  .page__content > :first-child { margin-top: 0.5rem; }
  .page__content h2 { margin-top: 1.25rem; margin-bottom: 0.5rem; border-bottom: none; padding-bottom: 0; }
</style>