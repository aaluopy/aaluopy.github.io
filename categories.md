---
layout: default
title: Categories
permalink: /categories/
---

<div class="container py-5">
  <h1 class="text-center mb-5">Categories</h1>
  
  {%- assign categories = site.categories | sort -%}
  {%- if categories.size > 0 -%}
    <div class="categories-grid">
      {%- for category in categories -%}
        <div class="category-section">
          <h2 class="category-title" id="{{ category[0] | slugify }}">
            {{ category[0] }}
            <span class="category-count">({{ category[1].size }})</span>
          </h2>
          
          <div class="category-posts">
            {%- for post in category[1] -%}
              <article class="category-post-item">
                <h3 class="post-title">
                  <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
                </h3>
                
                <div class="post-meta">
                  <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
                  {%- if post.author -%}
                    <span>by {{ post.author }}</span>
                  {%- endif -%}
                </div>
                
                <div class="post-excerpt">
                  {{ post.excerpt | strip_html | truncate: 150 }}
                </div>
                
                {%- if post.tags.size > 0 -%}
                  <div class="tags">
                    {%- for tag in post.tags -%}
                      <a href="{{ "/tags#" | append: tag | relative_url }}" class="tag">{{ tag }}</a>
                    {%- endfor -%}
                  </div>
                {%- endif -%}
              </article>
            {%- endfor -%}
          </div>
        </div>
      {%- endfor -%}
    </div>
  {%- else -%}
    <div class="text-center">
      <p>No categories yet. Check back soon!</p>
    </div>
  {%- endif -%}
</div>

<style>
.categories-grid {
  display: grid;
  gap: 3rem;
}

.category-section {
  background: var(--bg-primary);
  border-radius: var(--radius-lg);
  padding: 2rem;
  box-shadow: var(--shadow-sm);
  border: 1px solid var(--border-color);
}

.category-title {
  font-size: 1.75rem;
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 2px solid var(--primary-color);
  color: var(--text-primary);
}

.category-count {
  font-size: 1rem;
  color: var(--text-light);
  font-weight: 400;
}

.category-posts {
  display: grid;
  gap: 1.5rem;
}

.category-post-item {
  padding: 1.5rem;
  background: var(--bg-secondary);
  border-radius: var(--radius-md);
  transition: all 0.2s ease;
}

.category-post-item:hover {
  background: var(--bg-accent);
  transform: translateY(-2px);
}

.category-post-item .post-title {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.category-post-item .post-title a {
  color: var(--text-primary);
}

.category-post-item .post-meta {
  font-size: 0.875rem;
  color: var(--text-light);
  margin-bottom: 1rem;
  display: flex;
  gap: 1rem;
  align-items: center;
}

.category-post-item .post-excerpt {
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: 1rem;
}
</style>