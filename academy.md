---
permalink: /academy/
---

<style>
  @import url("https://api.mapbox.com/mapbox-gl-js/v3.15.0/mapbox-gl.css");

  .academic-map-layout {
    display: grid;
    grid-template-columns: minmax(260px, 320px) minmax(0, 1fr);
    gap: 1.75rem;
    align-items: stretch;
  }

  .academic-journey {
    border-top: 1px solid var(--line);
    padding-top: 1rem;
  }

  .journey-list {
    list-style: none;
    margin: 0;
    padding: 0;
    display: grid;
  }

  .journey-list li {
    display: grid;
    grid-template-columns: 2rem minmax(0, 1fr);
    gap: 0.85rem;
    padding: 0.95rem 0;
    border-top: 1px solid var(--line);
  }

  .journey-list li:first-child {
    border-top: none;
    padding-top: 0;
  }

  .journey-index {
    color: var(--muted);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    font-size: 0.92rem;
    line-height: 1.6;
  }

  .journey-copy {
    min-width: 0;
  }

  .journey-place {
    margin: 0;
    font-size: 1rem;
    line-height: 1.45;
  }

  .journey-city,
  .journey-note {
    margin: 0;
    color: var(--muted);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    font-size: 0.92rem;
    line-height: 1.55;
  }

  .academic-map-shell {
    border: 1px solid var(--line);
    background: var(--surface);
    overflow: hidden;
  }

  .academic-map-frame {
    width: 100%;
    height: 620px;
    min-height: 520px;
  }

  .journey-marker {
    width: 1.85rem;
    height: 1.85rem;
    border-radius: 999px;
    border: 1px solid rgba(0, 0, 0, 0.15);
    background: rgba(255, 255, 255, 0.96);
    color: #111;
    display: grid;
    place-items: center;
    font-size: 0.82rem;
    font-weight: 600;
    box-shadow: 0 1px 6px rgba(0, 0, 0, 0.08);
  }

  .mapboxgl-popup-content {
    padding: 0.8rem 0.9rem;
    border-radius: 0;
    box-shadow: none;
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  }

  .map-popup-title {
    margin: 0 0 0.2rem;
    font-size: 0.95rem;
    font-weight: 600;
    line-height: 1.4;
  }

  .map-popup-meta {
    margin: 0;
    color: #666;
    font-size: 0.86rem;
    line-height: 1.45;
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
      <ol class="journey-list">
        <li>
          <div class="journey-index">01</div>
          <div class="journey-copy">
            <p class="journey-place"><strong>Alma Mater Studiorum – University of Bologna</strong></p>
            <p class="journey-city">Bologna, Italy</p>
            <p class="journey-note">Bachelor’s degree in Computer Science</p>
          </div>
        </li>

        <li>
          <div class="journey-index">02</div>
          <div class="journey-copy">
            <p class="journey-place"><strong>University of Hull</strong></p>
            <p class="journey-city">Hull, United Kingdom</p>
            <p class="journey-note">Exchange Program</p>
          </div>
        </li>

        <li>
          <div class="journey-index">03</div>
          <div class="journey-copy">
            <p class="journey-place"><strong>Deloitte</strong></p>
            <p class="journey-city">Milan, Italy</p>
            <p class="journey-note">Consulting</p>
          </div>
        </li>

        <li>
          <div class="journey-index">04</div>
          <div class="journey-copy">
            <p class="journey-place"><strong>Imperial College London</strong></p>
            <p class="journey-city">London, United Kingdom</p>
            <p class="journey-note">Master’s studies in Computer Science</p>
          </div>
        </li>

        <li>
          <div class="journey-index">05</div>
          <div class="journey-copy">
            <p class="journey-place"><strong>Sapienza University of Rome</strong></p>
            <p class="journey-city">Rome, Italy</p>
            <p class="journey-note">Master’s studies in Applied Mathematics</p>
          </div>
        </li>

        <li>
          <div class="journey-index">06</div>
          <div class="journey-copy">
            <p class="journey-place"><strong>Technical University of Munich</strong></p>
            <p class="journey-city">Munich, Germany</p>
            <p class="journey-note">Exchange Program</p>
          </div>
        </li>

        <li>
          <div class="journey-index">07</div>
          <div class="journey-copy">
            <p class="journey-place"><strong>University of Warwick</strong></p>
            <p class="journey-city">Coventry, United Kingdom</p>
            <p class="journey-note">PhD in Mathematics</p>
          </div>
        </li>
      </ol>
    </div>

    <div class="academic-map-shell">
      <div id="academic-map" class="academic-map-frame" aria-label="Academic map"></div>
    </div>
  </div>
</section>

<section class="section-block">
  <p class="section-label">PUBLICATIONS</p>

  <div class="publications-grid">
    {% for pub in site.data.publications %}
      <article class="publication-card">
        <div class="publication-media">
          <img src="{{ pub.image | relative_url }}" alt="{{ pub.image_alt | default: pub.title | escape }}" loading="lazy">
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

<script src="https://api.mapbox.com/mapbox-gl-js/v3.15.0/mapbox-gl.js"></script>
<script>
  document.addEventListener("DOMContentLoaded", function () {
    const mapEl = document.getElementById("academic-map");
    if (!mapEl || typeof mapboxgl === "undefined") return;

    mapboxgl.accessToken = "pk.eyJ1Ijoia2V2aW5tYW5jaW5pIiwiYSI6ImNrbmxycTBpODBnODgzMXFwM2g5eGluaXoifQ.CDOZybMCLF7KQAaHYWRhaQ";

    const europeBounds = [
      [-31.5, 34.0],
      [40.5, 72.5]
    ];

    const journey = [
      {
        institution: "Alma Mater Studiorum – University of Bologna",
        city: "Bologna, Italy",
        role: "Bachelor’s degree in Computer Science",
        coordinates: [11.3426, 44.4949]
      },
      {
        institution: "University of Hull",
        city: "Hull, United Kingdom",
        role: "Exchange Program",
        coordinates: [-0.3367, 53.7457]
      },
      {
        institution: "Deloitte",
        city: "Milan, Italy",
        role: "Consulting",
        coordinates: [9.19, 45.4642]
      },
      {
        institution: "Imperial College London",
        city: "London, United Kingdom",
        role: "Master’s studies in Computer Science",
        coordinates: [-0.1749, 51.4988]
      },
      {
        institution: "Sapienza University of Rome",
        city: "Rome, Italy",
        role: "Master’s studies in Applied Mathematics",
        coordinates: [12.5145, 41.9038]
      },
      {
        institution: "Technical University of Munich",
        city: "Munich, Germany",
        role: "Exchange Program",
        coordinates: [11.5676, 48.1483]
      },
      {
        institution: "University of Warwick",
        city: "Coventry, United Kingdom",
        role: "PhD in Mathematics",
        coordinates: [-1.5619, 52.3836]
      }
    ];

    const map = new mapboxgl.Map({
      container: "academic-map",
      style: "mapbox://styles/kevinmancini/cmmxc43e8003101sigd4j00tc",
      center: [10.5, 49.5],
      zoom: 3.9,
      maxBounds: europeBounds,
      scrollZoom: false
    });

    map.addControl(
      new mapboxgl.NavigationControl({ showCompass: false }),
      "top-right"
    );

    map.on("load", function () {
      journey.forEach(function (stop, index) {
        const marker = document.createElement("div");
        marker.className = "journey-marker";
        marker.textContent = String(index + 1).padStart(2, "0");

        const popup = new mapboxgl.Popup({ offset: 16 }).setHTML(
          `<p class="map-popup-title">${stop.institution}</p>
           <p class="map-popup-meta">${stop.city}<br>${stop.role}</p>`
        );

        new mapboxgl.Marker({ element: marker, anchor: "center" })
          .setLngLat(stop.coordinates)
          .setPopup(popup)
          .addTo(map);
      });
    });
  });
</script>