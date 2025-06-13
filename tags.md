---
layout: default
title: Tags
permalink: /tags/
---

<div class="container py-5">
  <h1 class="text-center mb-5">Tags</h1>
  
  {%- assign tags = site.tags | sort -%}
  {%- if tags.size > 0 -%}
    <div class="tag-cloud mb-5">
      {%- for tag in tags -%}
        <a href="#{{ tag[0] | slugify }}" class="tag-cloud-item" data-count="{{ tag[1].size }}">
          {{ tag[0] }}
          <span class="tag-count">{{ tag[1].size }}</span>
        </a>
      {%- endfor -%}
    </div>
    
    <div class="tags-sections">
      {%- for tag in tags -%}
        <div class="tag-section" id="{{ tag[0] | slugify }}">
          <h2 class="tag-title">
            {{ tag[0] }}
            <span class="tag-count-large">({{ tag[1].size }} posts)</span>
          </h2>
          
          <div class="tag-posts">
            {%- for post in tag[1] -%}
              <article class="tag-post-item">
                <h3 class="post-title">
                  <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
                </h3>
                
                <div class="post-meta">
                  <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
                  {%- if post.author -%}
                    <span>by {{ post.author }}</span>
                  {%- endif -%}
                  {%- if post.categories.size > 0 -%}
                    <span>in {{ post.categories | join: ", " }}</span>
                  {%- endif -%}
                </div>
                
                <div class="post-excerpt">
                  {{ post.excerpt | strip_html | truncate: 150 }}
                </div>
              </article>
            {%- endfor -%}
          </div>
        </div>
      {%- endfor -%}
    </div>
  {%- else -%}
    <div class="text-center">
      <p>No tags yet. Check back soon!</p>
    </div>
  {%- endif -%}
</div>

<style>
.tag-cloud {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.75rem;
  padding: 2rem;
  background: var(--bg-secondary);
  border-radius: var(--radius-lg);
  margin-bottom: 3rem;
}

.tag-cloud-item {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem 1rem;
  background: var(--bg-primary);
  color: var(--primary-color);
  text-decoration: none;
  border-radius: var(--radius-md);
  border: 1px solid var(--border-color);
  transition: all 0.2s ease;
  font-weight: 500;
}

.tag-cloud-item:hover {
  background: var(--primary-color);
  color: white;
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

.tag-count {
  background: var(--bg-accent);
  color: var(--text-secondary);
  padding: 0.125rem 0.5rem;
  border-radius: var(--radius-sm);
  font-size: 0.75rem;
  font-weight: 600;
}

.tag-cloud-item:hover .tag-count {
  background: rgba(255, 255, 255, 0.2);
  color: white;
}

.tags-sections {
  display: grid;
  gap: 3rem;
}

.tag-section {
  background: var(--bg-primary);
  border-radius: var(--radius-lg);
  padding: 2rem;
  box-shadow: var(--shadow-sm);
  border: 1px solid var(--border-color);
}

.tag-title {
  font-size: 1.75rem;
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 2px solid var(--accent-color);
  color: var(--text-primary);
}

.tag-count-large {
  font-size: 1rem;
  color: var(--text-light);
  font-weight: 400;
}

.tag-posts {
  display: grid;
  gap: 1.5rem;
}

.tag-post-item {
  padding: 1.5rem;
  background: var(--bg-secondary);
  border-radius: var(--radius-md);
  transition: all 0.2s ease;
}

.tag-post-item:hover {
  background: var(--bg-accent);
  transform: translateY(-2px);
}

.tag-post-item .post-title {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.tag-post-item .post-title a {
  color: var(--text-primary);
}

.tag-post-item .post-meta {
  font-size: 0.875rem;
  color: var(--text-light);
  margin-bottom: 1rem;
  display: flex;
  gap: 1rem;
  align-items: center;
}

.tag-post-item .post-excerpt {
  color: var(--text-secondary);
  line-height: 1.6;
}

/* Dynamic tag sizes based on post count */
.tag-cloud-item[data-count="1"] { font-size: 0.875rem; }
.tag-cloud-item[data-count="2"] { font-size: 0.9375rem; }
.tag-cloud-item[data-count="3"] { font-size: 1rem; }
.tag-cloud-item[data-count="4"] { font-size: 1.0625rem; }
.tag-cloud-item[data-count="5"] { font-size: 1.125rem; }
</style>