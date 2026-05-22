---
layout: default
title: Blog
permalink: /blog/
---

<section id="blog" style="padding-top: calc(64px + 4rem);">
  <div class="section-header fade-in">
    <h2>Blog</h2>
    <p>Thoughts on iOS development, architecture, and Apple technologies</p>
  </div>

  <div class="blog-posts fade-in">
    {% for post in site.posts limit: 10 %}
    <a href="{{ post.url | relative_url }}" class="blog-post-card">
      <div class="blog-post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%B %d, %Y' }}</time>
        {% for tag in post.tags %}
        <span class="blog-tag">{{ tag }}</span>
        {% endfor %}
      </div>
      <h3 class="blog-post-title">{{ post.title }}</h3>
      <p class="blog-post-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </a>
    {% endfor %}

    {% if site.posts == empty %}
    <div class="no-posts">
      <p>Coming soon. Stay tuned!</p>
    </div>
    {% endif %}
  </div>
</section>

<style>
  .blog-posts {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    max-width: 720px;
    margin: 0 auto;
  }

  .blog-post-card {
    display: block;
    background: #2C2C2E;
    border: 1px solid #3A3A3C;
    border-radius: 16px;
    padding: 1.5rem 1.75rem;
    transition: all 0.3s ease;
  }

  .blog-post-card:hover {
    border-color: #48484A;
    background: #353537;
    transform: translateY(-3px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.25);
  }

  .blog-post-meta {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin-bottom: 0.6rem;
    flex-wrap: wrap;
  }

  .blog-post-meta time {
    font-size: 0.825rem;
    font-weight: 500;
    color: #6E6E73;
  }

  .blog-tag {
    font-size: 0.75rem;
    font-weight: 600;
    color: #2997FF;
    background: rgba(41, 151, 255, 0.1);
    padding: 0.2rem 0.6rem;
    border-radius: 6px;
    text-transform: lowercase;
  }

  .blog-post-title {
    font-size: 1.2rem;
    font-weight: 700;
    color: #F5F5F7;
    margin-bottom: 0.4rem;
    letter-spacing: -0.02em;
  }

  .blog-post-excerpt {
    font-size: 0.925rem;
    color: #A1A1A6;
    line-height: 1.6;
  }

  .no-posts {
    text-align: center;
    padding: 4rem 2rem;
    color: #6E6E73;
    font-size: 1.1rem;
  }

  @media (max-width: 768px) {
    .blog-post-card {
      padding: 1.25rem;
    }
  }
</style>
