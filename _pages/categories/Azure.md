---
title: "카테고리: Azure"
layout: archive
permalink: /azure/
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