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