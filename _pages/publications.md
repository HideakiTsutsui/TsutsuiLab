---
title: "Publications"
layout: single
permalink: /publications/
---

For the latest publications list, please check [Google Scholar](https://scholar.google.com/citations?user=Trw76bsAAAAJ&hl=en).

## Journal Publications

{% assign pubs = site.data.publications | sort: "date" | reverse %}
{% assign count = pubs | size %}

[//]: # "Use this for a reversed list <ol reversed>"
<ol>
{% for pub in pubs %}
  <li>
    {{ pub.authors }} ({{ pub.year }}). {{ pub.title }}. <i><strong>{{ pub.venue }}</strong></i>. {{ pub.volume }} {{ pub.page }}.
    {% if pub.doi %}
      <a href="https://doi.org/{{ pub.doi }}" target="_blank">DOI</a>
    {% elsif pub.url %}
      <a href="{{ pub.url }}" target="_blank">Link</a>
    {% endif %}
  </li>
{% endfor %}
</ol>
