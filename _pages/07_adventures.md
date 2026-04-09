---
layout: page
title: Adventures
description: An overview of a few of my travels and adventures.
permalink: /adventures/
background: '/images/main_pages/IMG_8878.JPEG'
---

{% for post in site.adventures %}

<article class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
        <h2 class="post-title">{{ post.title }}</h2>
        {% if post.subtitle %}
        <h3 class="post-subtitle">{{ post.subtitle }}</h3>
        {% else %}
        <h3 class="post-subtitle">
            {{ post.excerpt | strip_html | truncatewords: 15 }}
        </h3>
        {% endif %}
    </a>
    <p class="post-meta">
        {{ post.date | date: '%B %d, %Y' }} · {% include
        read_time.html content=post.content %}
    </p>
</article>

<hr />

{% endfor %}