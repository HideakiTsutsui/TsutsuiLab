---
title: "Photo Gallery"
layout: single
classes: wide
permalink: /photos/
---

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.gallery-grid figure {
  margin: 0;
  text-align: center;
}

.gallery-grid img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.gallery-grid figcaption {
  font-size: 0.9rem;
  color: #444;
  margin-top: 0.5rem;
}
</style>

## Team Photo Archive

{% assign sorted_photos = site.data.photos | sort: "year" | reverse %}

{% for year_group in sorted_photos %}
### {{ year_group.year }}

{% for event in year_group.events %}
#### {{ event.title }}

<div class="gallery-grid">
  {% for img in event.images %}
    <figure>
      <img src="{{ img.path }}" alt="{{ img.caption }}">
      <figcaption>{{ img.caption }}</figcaption>
    </figure>
  {% endfor %}
</div>

{% endfor %}

---
{% endfor %}
