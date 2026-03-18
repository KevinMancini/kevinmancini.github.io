---
title: Sport
permalink: /sport/
kicker: Journal
intro: Climbing, alpinism, trekking, running, diving, and travel — collected as a simple archive of stories and photographs.
---

<div class="callout">
  <p>This page is meant to stay easy to update. Add a new Markdown file to <code>_sport/</code>, commit it, and it will appear automatically.</p>
</div>

{% assign posts = site.sport | sort: 'date' | reverse %}
{% if posts.size > 0 %}
  <div class="archive-list">
    {% for post in posts %}
      <a class="archive-item" href="{{ post.url | relative_url }}">
        <div class="archive-date">{{ post.date | date: "%d %b %Y" }}</div>
        <div class="archive-content">
          <h3>{{ post.title }}</h3>
          <p class="meta">{% if post.location %}{{ post.location }}{% else %}Sport journal{% endif %}</p>
          <p>{{ post.excerpt | default: post.content | strip_html | strip_newlines | truncate: 170 }}</p>
        </div>
      </a>
    {% endfor %}
  </div>
{% else %}
  <div class="empty-state panel">
    <p>No sport entries yet.</p>
    <p class="muted">Copy <code>templates/sport-post-template.md</code> into <code>_sport/</code>, rename it, and start writing.</p>
  </div>
{% endif %}
