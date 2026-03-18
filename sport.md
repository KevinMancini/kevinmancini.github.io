---
title: Sport
permalink: /sport/
kicker: Journal
intro: A home for climbing, alpinism, trekking, running, diving, and travel stories — designed to be updated post by post.
---

<div class="panel callout">
  <p>This page works like a clean archive. Add a new Markdown file to <code>_sport/</code>, commit it to GitHub, and the post will appear automatically here and on the home page.</p>
</div>

{% assign posts = site.sport | sort: 'date' | reverse %}
{% if posts.size > 0 %}
  <div class="post-grid">
    {% for post in posts %}
      <a class="panel post-card" href="{{ post.url | relative_url }}">
        {% if post.cover_image %}
          <img class="post-card-image" src="{{ post.cover_image | relative_url }}" alt="{{ post.title }}" />
        {% else %}
          <div class="post-card-placeholder">Sport</div>
        {% endif %}
        <div class="post-card-body">
          <p class="meta">{{ post.date | date: "%d %b %Y" }}{% if post.location %} · {{ post.location }}{% endif %}</p>
          <h3>{{ post.title }}</h3>
          <p>{{ post.excerpt | default: post.content | strip_html | strip_newlines | truncate: 140 }}</p>
        </div>
      </a>
    {% endfor %}
  </div>
{% else %}
  <div class="panel empty-state">
    <p>No sport entries yet.</p>
    <p class="muted">Copy <code>templates/sport-post-template.md</code> into <code>_sport/</code>, rename it, and start writing.</p>
  </div>
{% endif %}
