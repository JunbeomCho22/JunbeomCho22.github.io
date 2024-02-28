---
title: "카테고리: Python"
layout: archive
permalink: /python/
author_profile: true
sidebar_main: true
---

<div class="grid__wrapper">
    {% assign posts = site.categories.python %}
    {% for post in posts %}
        {% include archive-single3.html type="list" %}
    {% endfor %}
</div>

{% include paginator.html %}