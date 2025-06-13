---
layout: default
title: Posts
permalink: /posts/
---

<div class="container py-5">
  <h1 class="text-center mb-5">All Posts</h1>
  
  {%- if site.posts.size > 0 -%}
    <div class="post-list">
      {%- for post in site.posts -%}
        <article class="post-item">
          <h2 class="post-title">
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
          </h2>
          
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
            {{ post.excerpt | strip_html | truncate: 300 }}
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
  {%- else -%}
    <div class="text-center">
      <p>No posts yet. Check back soon!</p>
    </div>
  {%- endif -%}
</div>

<style>
.post-preview {
  margin-bottom: 2rem;
  padding-bottom: 1.5rem;
  border-bottom: 1px solid #e8e8e8;
}

.post-preview:last-child {
  border-bottom: none;
}

.post-preview h2 {
  margin-bottom: 0.5rem;
}

.post-meta {
  color: #828282;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.post-meta a {
  color: #0366d6;
  text-decoration: none;
}

.post-meta a:hover {
  text-decoration: underline;
}

.post-excerpt {
  color: #666;
  line-height: 1.6;
}
</style>