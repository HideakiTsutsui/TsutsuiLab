---
title: "Research"
layout: single
classes: single
permalink: /research/
---

## Ongoing Projects

{% for research in site.data.research %}
### {{ research.title }}

![{{ research.title }}]({{ research.image }}){: style="float: left; margin-right: 1rem; width: 300px;" } {{ research.summary }}

<div style="clear: both;"></div>

---
{% endfor %}

## Our Sponsors

![Our Sponsors](../assets/images/research/Sponsors.png){: .center width="100%" }
