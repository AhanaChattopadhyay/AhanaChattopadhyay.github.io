---
layout: default
title: "Blogs"
permalink: /blogs/
---

<style>
  .archive-list {
    margin: 0;
    padding: 0;
  }

  .archive-list > div {
    display: grid;
    grid-template-columns: 120px minmax(0, 1fr);
    gap: 18px;
    align-items: baseline;
    margin-bottom: 18px;
  }

  .archive-list time {
    color: var(--muted, #9aa0b5);
    white-space: nowrap;
  }

  .archive-list a {
    font-size: 1.05rem;
    font-weight: 700;
    text-decoration: none;
  }

  .archive-list a:hover {
    text-decoration: underline;
  }

  @media (max-width: 480px) {
    .archive-list > div {
      grid-template-columns: 1fr;
      gap: 4px;
    }
  }
</style>

<main>
  <header>
    <h1>{{ page.title }}</h1>
  </header>

  <nav class="archive-list">
    {% for post in site.posts %}
      <div>
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%Y-%m-%d" }}
        </time>

        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
      </div>
    {% endfor %}
  </nav>
</main>
