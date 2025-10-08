---
layout: home
---
<style>
/* This block will override all theme styles for your article list */
.flex-container {
  display: flex !important;
  align-items: flex-start !important;
  gap: 20px !important;
  margin-bottom: 30px !important;
}

.article-thumbnail-wrapper {
  flex-shrink: 0 !important; 
  width: 150px !important;
  height: 100px !important;
}

img.article-thumbnail { 
  width: 100% !important; 
  height: 100% !important;
  max-width: 100% !important; /* Final nail in the coffin for the max-width: 100% rule */
  object-fit: cover !important;
  border-radius: 4px;
}

.article-text-content.flex-grow {
  flex-grow: 1 !important; 
  min-width: 0 !important; 
}
</style>
# Latest Articles

{% assign sorted_articles = site.articles | sort: 'date' | reverse %}
{% for article in sorted_articles limit: 5 %}
  <div class="article-listing-item flex-container">  {% if article.thumbnail %}
    <div class="article-thumbnail-wrapper"> 
      <img 
        src="{{ article.thumbnail }}" 
        alt="{{ article.title }} Thumbnail" 
        class="article-thumbnail"
        loading="lazy"
      >
    </div>
  {% endif %}

  <div class="article-text-content flex-grow"> <h2><a href="{{ article.external_url }}" target="_blank" rel="noopener noreferrer">{{ article.title }}</a></h2>

      <p>
          <strong>{{ article.publication }}</strong> <span class="text-muted">| {{ article.date | date: "%B %d, %Y" }}</span>
      </p>

      <p>{{ article.excerpt }}</p>

      <p><a href="{{ article.external_url }}" target="_blank" rel="noopener noreferrer">Read the Full Article &rarr;</a></p>
  </div>
  
  <hr>
</div>
{% endfor %}

<p class="text-center">
  <a href="{{ '/articles/' | relative_url }}">View All Published Articles &rarr;</a>
</p>