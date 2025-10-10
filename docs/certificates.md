---
layout: default
title: Certificates
nav_order: 9
---

# Certificates

---

<div class="cert-grid">
{% assign sorted = site.data.certificates | sort: "year" | reverse %}
{% for cert in sorted %}
  <div class="cert-card">
    {% if cert.pdf %}
      <a href="{{ cert.pdf }}" target="_blank" rel="noopener">
        <img src="{{ cert.image }}" alt="{{ cert.name }}" width="240">
      </a>
    {% else %}
      <img src="{{ cert.image }}" alt="{{ cert.name }}" width="240">
    {% endif %}
    <p><strong>{{ cert.name }}</strong><br>
    <em>{{ cert.provider }}, {{ cert.month }} {{ cert.year }}</em></p>
    {% if cert.pdf %}
      <p><a href="{{ cert.pdf }}" target="_blank" rel="noopener">📄 View PDF</a></p>
    {% endif %}
  </div>
{% endfor %}
</div>

<style>
.cert-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;     /* ✅ center the rows */
  gap: 2rem;
  max-width: 900px;            /* ✅ about 3 cards per line on desktop */
  margin: 0 auto;
}

.cert-card {
  flex: 0 1 calc(33.333% - 2rem);  /* ✅ 3 per row on PC */
  box-sizing: border-box;
  text-align: center;
}

.cert-card img {
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  transition: transform 0.2s ease;
  max-width: 100%;
  height: auto;
}

.cert-card img:hover {
  transform: scale(1.03);
}

.cert-card a {
  text-decoration: none;
  color: inherit;
}

.cert-card p {
  margin: .4rem 0;
  font-size: .9rem;
}

/* ✅ Responsive layout for tablets/phones */
@media (max-width: 900px) {
  .cert-card {
    flex: 0 1 calc(50% - 1.5rem);  /* 2 per row */
  }
}

@media (max-width: 600px) {
  .cert-grid {
    flex-direction: column;
    align-items: center;          /* ✅ center single-column layout */
  }
  .cert-card {
    flex: 0 1 90%;
    max-width: 300px;
  }
}
</style>
