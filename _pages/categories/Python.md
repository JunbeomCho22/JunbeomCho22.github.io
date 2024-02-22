---
title: "카테고리: Python"
layout: archive
permalink: categories/python
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.python %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}