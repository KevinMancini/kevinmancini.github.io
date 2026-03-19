---
title: Academy
permalink: /academy/
kicker: Academic profile
intro: A map of where I studied and a selection of publications.
---

<style>
  .academy-link-row {
    display: flex;
    flex-wrap: wrap;
    gap: 0.9rem;
    margin: 0 0 2rem;
  }

  .academy-link {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    padding: 0.8rem 1rem;
    border: 1px solid var(--line);
    background: var(--surface);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    font-size: 0.95rem;
    color: var(--muted);
  }

  .academy-link:hover {
    color: var(--text);
  }

  .academic-map-shell {
    border: 1px solid var(--line);
    background: var(--surface);
    overflow: hidden;
  }

  .academic-map-frame {
    display: block;
    width: 100%;
    height: min(68vh, 620px);
    min-height: 430px;
    border: none;
  }

  .publications-grid {
    display: grid;
    gap: 1.75rem;
  }

  .publication-card {
    display: grid;
    grid-template-columns: minmax(220px, 320px) minmax(0, 1fr);
    gap: 1.5rem;
    align-items: start;
    border-top: 1px solid var(--line);
    padding-top: 1.25rem;
  }

  .publication-media {
    background: var(--surface);
    border: 1px solid var(--line);
    aspect-ratio: 4 / 3;
    overflow: hidden;
  }

  .publication-media img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transform: scale(1.01);
  }

  .publication-meta {
    margin: 0 0 0.45rem;
    color: var(--muted);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    font-size: 0.88rem;
  }

  .publication-title {
    margin: 0 0 0.75rem;
  }

  .publication-summary {
    margin: 0 0 1rem;
  }

  .publication-links {
    display: flex;
    flex-wrap: wrap;
    gap: 0.8rem 1rem;
  }

  .publication-links a {
    color: var(--muted);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    font-size: 0.92rem;
  }

  .publication-links a:hover {
    color: var(--text);
  }

  @media (max-width: 780px) {
    .publication-card {
      grid-template-columns: 1fr;
    }

    .academic-map-frame {
      min-height: 360px;
      height: 56vh;
    }
  }
</style>

<div class="academy-link-row">
  <a class="academy-link" href="{{ site.data.profile.cv }}" target="_blank" rel="noopener">Curriculum vitae</a>
</div>

<section class="section-block">
  <div class="section-head">
    <div>
      <p class="section-label">Map</p>
      <h2>Where I studied</h2>
    </div>
  </div>

  <div class="academic-map-shell">
<iframe width='100%' height='400px' src="https://api.mapbox.com/styles/v1/kevinmancini/cmmxc43e8003101sigd4j00tc.html?title=false&access_token=pk.eyJ1Ijoia2V2aW5tYW5jaW5pIiwiYSI6ImNrbmxycTBpODBnODgzMXFwM2g5eGluaXoifQ.CDOZybMCLF7KQAaHYWRhaQ&zoomwheel=false#2/38/-34" title="Academy" style="border:none;"></iframe>
  </div>
</section>

<section class="section-block">
  <div class="section-head">
    <div>
      <p class="section-label">Publications</p>
      <h2>Selected work</h2>
    </div>
  </div>

  <div class="publications-grid">
    {% for pub in site.data.publications %}
      <article class="publication-card">
        <div class="publication-media">
          <img src="{{ pub.image }}" alt="{{ pub.image_alt | escape }}" loading="lazy">
        </div>

        <div class="publication-copy">
          <p class="publication-meta">{{ pub.authors }} · {{ pub.venue }} · {{ pub.year }}</p>
          <h3 class="publication-title">{{ pub.title }}</h3>
          <p class="publication-summary">{{ pub.summary }}</p>

          <div class="publication-links">
            {% for link in pub.links %}
              <a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>
            {% endfor %}
          </div>
        </div>
      </article>
    {% endfor %}
  </div>
</section>