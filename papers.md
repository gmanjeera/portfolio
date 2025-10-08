---
layout: page
title: Academic Papers
permalink: /papers/
---



{% assign sorted_papers = site.papers | sort: 'date' | reverse %}

{% for paper in sorted_papers %}
<div class="paper-listing">
  <h2><a href="{{ paper.external_url | relative_url }}">{{ paper.title }}</a></h2>

  <p class="meta">
    Authored by: <strong>{{ paper.authors | join: ", " }}</strong> <br>
    Published in <strong>{{ paper.journal }}</strong>, {{ paper.date | date: "%Y" }}
  </p>

  <p>{{ paper.abstract | markdownify | truncatewords: 30 }}</p>

  <a href="{{ paper.external_url | relative_url }}" class="read-more">Read Abstract & Details &rarr;</a>

  </div>
<hr>
{% endfor %}