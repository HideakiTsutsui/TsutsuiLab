---
title: "Our Team"
layout: single
permalink: /team/
---

<style>
.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
}

.team-card {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  background: #f9f9f9;
  padding: 1rem;
  border-radius: 0.75rem;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
  min-width: 0; /* allows text to wrap inside grid column */
}

.team-card img {
  border-radius: 50%;
  width: 100px;
  height: 100px;
  object-fit: cover;
  aspect-ratio: 1 / 1;
  flex-shrink: 0;
}
</style>

## Principal Investigator

<div class="team-grid">
{% assign principal_investigator = site.data.team | where: "status", "PI" | sort: "year_joined" %}
{% for member in principal_investigator %}
  <div class="team-card">
    <img src="{{ member.image }}" alt="{{ member.name }}">
    <div>
      <strong>{{ member.name }}</strong><br>
      <em>{{ member.role }}</em><br>
      {% if member.email %}
        📧 <a href="mailto:{{ member.email }}">{{ member.email }}</a><br>
      {% endif %}
      {% if member.cv %}
        📄 <a href="{{ member.cv }}" target="_blank">CV</a><br>
      {% endif %}
      {% if member.scholar %}
        🔗 <a href="{{ member.scholar }}" target="_blank">Google Scholar</a><br>
      {% endif %}
      {% if member.scholar %}
        <a href="{{ member.scholar }}" target="_blank" style="text-decoration: none;">
          <span style="color: #4285F4; font-weight: bold; font-size: 1.1em;">g</span>
          <span style="margin-left: 0.2em;">Google Scholar</span>
        </a><br>
      {% endif %}
      {{ member.bio }}
    </div>
  </div>
{% endfor %}
</div>

## Current Members

<div class="team-grid">
{% assign current_members = site.data.team | where: "status", "current" | sort: "year_joined" %}
{% for member in current_members %}
  <div class="team-card">
    <img src="{{ member.image }}" alt="{{ member.name }}">
    <div>
      <strong>{{ member.name }}</strong><br>
      <em>{{ member.role }}</em><br>
      {% if member.email %}
        📧 <a href="mailto:{{ member.email }}">{{ member.email }}</a><br>
      {% endif %}
      {{ member.bio }}
    </div>
  </div>
{% endfor %}
</div>

## Previous Members

### Postdocs

{% assign postdocs = site.data.team | where: "status", "alumni" | where: "position", "postdoc" | sort: "year_left" | reverse %}
{% for member in postdocs %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }} 
{% endfor %}
---

### Graduate Students

{% assign grads = site.data.team | where: "status", "alumni" | where: "position", "grad" | sort: "year_left" | reverse %}
{% for member in grads %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }} 
{% endfor %}
---

### Undergraduate Students

{% assign undergrads = site.data.team | where: "status", "alumni" | where: "position", "undergrad" | sort: "year_left" | reverse %}
{% for member in undergrads %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }}
{% endfor %}
---

### Exchange Students and Visitors

{% assign visitors = site.data.team | where: "status", "alumni" | where: "position", "visitor" | sort: "year_left" | reverse %}
{% for member in visitors %}
{{ member.name }}, {{ member.year_left }}, {{ member.role }}
{% endfor %}
