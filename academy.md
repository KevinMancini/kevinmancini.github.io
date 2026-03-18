---
title: Academy
permalink: /academy/
kicker: Academic profile
intro: A structured overview of background, education, research, selected publications, talks, and links.
---

<div class="split-grid">
  <div class="panel">
    <p class="mini-heading">Profile</p>
    <p>{{ site.data.profile.summary }}</p>
    <p>{{ site.data.profile.research_focus }}</p>
    <p>{{ site.data.profile.current_note }}</p>
  </div>
  <div class="panel">
    <p class="mini-heading">Quick links</p>
    <div class="link-list">
      <a href="{{ site.data.profile.cv }}">Curriculum vitae</a>
      <a href="{{ site.data.profile.scholar }}">Google Scholar</a>
      <a href="{{ site.data.profile.linkedin }}">LinkedIn</a>
      <a href="{{ site.data.profile.github }}">GitHub</a>
      <a href="mailto:{{ site.data.profile.email }}">{{ site.data.profile.email }}</a>
    </div>
  </div>
</div>

## Education

<div class="timeline">
  {% for item in site.data.education %}
    <div class="timeline-item panel">
      <div class="timeline-top">
        <h3>{{ item.institution }}</h3>
        <span>{{ item.years }}</span>
      </div>
      <p class="meta">{{ item.degree }} · {{ item.place }}</p>
      <ul>
        {% for detail in item.details %}
          <li>{{ detail }}</li>
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</div>

## Research and projects

<div class="timeline">
  {% for item in site.data.research %}
    <div class="timeline-item panel">
      <div class="timeline-top">
        <h3>{{ item.role }}</h3>
        <span>{{ item.years }}</span>
      </div>
      <p class="meta">{{ item.place }}</p>
      <ul>
        {% for detail in item.details %}
          <li>{{ detail }}</li>
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</div>

## Selected publications

<div class="stack">
  {% for pub in site.data.publications %}
    <div class="panel publication-card">
      <h3>{{ pub.title }}</h3>
      <p class="meta">{{ pub.authors }} · {{ pub.venue }} · {{ pub.year }}</p>
      <div class="button-row tight">
        {% for link in pub.links %}
          <a class="button small" href="{{ link.url }}">{{ link.label }}</a>
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>

## Talks

<div class="card-grid two-up">
  {% for talk in site.data.talks %}
    <div class="panel">
      <p class="mini-heading">{{ talk.date }}</p>
      <h3>{{ talk.title }}</h3>
      <p>{{ talk.venue }} · {{ talk.place }}</p>
    </div>
  {% endfor %}
</div>

## Experience

<div class="timeline">
  {% for item in site.data.experience %}
    <div class="timeline-item panel">
      <div class="timeline-top">
        <h3>{{ item.company }}</h3>
        <span>{{ item.years }}</span>
      </div>
      <p class="meta">{{ item.role }} · {{ item.place }}</p>
      <ul>
        {% for detail in item.details %}
          <li>{{ detail }}</li>
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</div>

## Honors and awards

<div class="split-grid">
  <div class="panel">
    <p class="mini-heading">Academic excellence</p>
    <ul class="simple-list">
      {% for item in site.data.awards.academic %}
        <li><strong>{{ item.date }}</strong> — {{ item.text }}</li>
      {% endfor %}
    </ul>
  </div>
  <div class="panel">
    <p class="mini-heading">Other distinctions</p>
    <ul class="simple-list">
      {% for item in site.data.awards.other %}
        <li><strong>{{ item.date }}</strong> — {{ item.text }}</li>
      {% endfor %}
    </ul>
  </div>
</div>
