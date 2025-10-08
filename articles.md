---
layout: page
title: Articles
permalink: /articles/
---

{% for article in site.articles reversed %}
  <div class="article-listing-item">
    <h2><a href="{{ article.external_url }}" target="_blank" rel="noopener noreferrer">{{ article.title }}</a></h2>
    <p>
      <strong>Published in:</strong> {{ article.publication }} 
      <span class="text-muted">| {{ article.date | date: "%B %d, %Y" }}</span>
    </p>
    <p>{{ article.excerpt }}</p>
    <p><a href="{{ article.external_url }}" target="_blank" rel="noopener noreferrer">Read the Full Article &rarr;</a></p>
    <hr>
  </div>
{% endfor %}