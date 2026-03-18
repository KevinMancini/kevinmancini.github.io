---
title: Art
permalink: /art/
kicker: Journal
intro: Classical music, piano notes, essays, and writing fragments — built as a quiet archive that can grow one post at a time.
---

<div class="callout">
  <p>This section works best for reflections, repertoire notes, essays, and drafts. Add a new file to <code>_art/</code> and it will be listed automatically.</p>
</div>

{% assign posts = site.art | sort: 'date' | reverse %}
{% if posts.size > 0 %}
  <div class="archive-list">
    {% for post in posts %}
      <a class="archive-item" href="{{ post.url | relative_url }}">
        <div class="archive-date">{{ post.date | date: "%d %b %Y" }}</div>
        <div class="archive-content">
          <h3>{{ post.title }}</h3>
          <p class="meta">{% if post.location %}{{ post.location }}{% else %}Art journal{% endif %}</p>
          <p>{{ post.excerpt | default: post.content | strip_html | strip_newlines | truncate: 170 }}</p>
        </div>
      </a>
    {% endfor %}
  </div>
{% else %}
  <div class="empty-state panel">
    <p>No art entries yet.</p>
    <p class="muted">Copy <code>templates/art-post-template.md</code> into <code>_art/</code>, rename it, and start writing.</p>
  </div>
{% endif %}
