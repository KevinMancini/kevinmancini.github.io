---
title: Academy
permalink: /academy/
kicker: Academic profile
intro: A map of where I studied and a selection of publications.
---

<style>
  .academic-map-layout {
    display: grid;
    grid-template-columns: minmax(180px, 220px) minmax(0, 1fr);
    gap: 1.5rem;
    align-items: stretch;
  }

  .academic-journey {
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-top: 1px solid var(--line);
    padding-top: 1rem;
  }

  .journey-list {
    list-style: none;
    margin: 0;
    padding: 0;
    display: grid;
    gap: 0.9rem;
  }

  .journey-list li {
    display: grid;
    gap: 0.15rem;
  }

  .journey-place {
    font-size: 1rem;
    margin: 0;
  }

  .journey-note {
    margin: 0;
    color: var(--muted);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    font-size: 0.92rem;
  }

  .academic-map-shell {
    border: 1px solid var(--line);
    background: var(--surface);
    overflow: hidden;
  }

  .academic-map-frame {
    display: block;
    width: 100%;
    height: 620px;
    min-height: 520px;
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

  @media (max-width: 900px) {
    .academic-map-layout {
      grid-template-columns: 1fr;
    }

    .academic-map-frame {
      height: 540px;
      min-height: 420px;
    }
  }

  @media (max-width: 780px) {
    .publication-card {
      grid-template-columns: 1fr;
    }

    .academic-map-frame {
      height: 460px;
      min-height: 360px;
    }
  }
</style>

<section class="section-block">
  <p class="section-label">MAP</p>

  <div class="academic-map-layout">
    <div class="academic-journey">
      <ul class="journey-list">
        <li>
          <p class="journey-place">Bologna</p>
          <p class="journey-note">Bachelor's studies</p>
        </li>
        <li>
          <p class="journey-place">Rome</p>
          <p class="journey-note">Master's studies</p>
        </li>
        <li>
          <p class="journey-place">London</p>
          <p class="journey-note">Research and study period</p>
        </li>
        <li>
          <p class="journey-place">Warwick</p>
          <p class="journey-note">PhD, starting in 2027</p>
        </li>
      </ul>
    </div>

    <div class="academic-map-shell">
      <iframe
        class="academic-map-frame"
        width="100%"
        height="400px"
        src="https://api.mapbox.com/styles/v1/kevinmancini/cmmxc43e8003101sigd4j00tc.html?title=false&access_token=pk.eyJ1Ijoia2V2aW5tYW5jaW5pIiwiYSI6ImNrbmxycTBpODBnODgzMXFwM2g5eGluaXoifQ.CDOZybMCLF7KQAaHYWRhaQ&zoomwheel=false#3.39/46.77/4.95"
        title="Academy"
        style="border:none;">
      </iframe>
    </div>
  </div>
</section>

<section class="section-block">
  <p class="section-label">PUBLICATIONS</p>

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