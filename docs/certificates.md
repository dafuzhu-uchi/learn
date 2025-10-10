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
  gap: 1.5rem;
}
.cert-card {
  flex: 0 1 240px;
  text-align: center;
}
.cert-card img {
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  transition: transform 0.2s ease;
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
</style>
