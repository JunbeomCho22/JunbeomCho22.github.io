---
title: "카테고리: Blog"
layout: archive
permalink: /blog/
author_profile: true
sidebar_main: true
---

<div class="grid__wrapper">
{% for category in site.categories %}
    <ul>
    {% for post in category[1] %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
    </ul>
{% endfor %}
</div>