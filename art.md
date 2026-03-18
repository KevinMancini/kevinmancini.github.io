---
title: Art
permalink: /art/
kicker: Journal
intro: A space for classical music, piano notes, essays, and writing fragments — built with the same post-by-post workflow as the sport section.
---

<div class="panel callout">
  <p>This section is ideal for repertoire reflections, concert notes, drafts, essays, and excerpts. Add a new Markdown file to <code>_art/</code> and it will be listed automatically.</p>
</div>

{% assign posts = site.art | sort: 'date' | reverse %}
{% if posts.size > 0 %}
  <div class="post-grid">
    {% for post in posts %}
      <a class="panel post-card" href="{{ post.url | relative_url }}">
        {% if post.cover_image %}
          <img class="post-card-image" src="{{ post.cover_image | relative_url }}" alt="{{ post.title }}" />
        {% else %}
          <div class="post-card-placeholder">Art</div>
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
    <p>No art entries yet.</p>
    <p class="muted">Copy <code>templates/art-post-template.md</code> into <code>_art/</code>, rename it, and start writing.</p>
  </div>
{% endif %}
