---
layout: doc
title: "Article System"
description: Self-contained, semantic layout structure powered
categories: ["Getting Started"]
permalink: /docs/article/
nav_order: 2
tags: ["Block", "Article", "UX Design"]
banner-image: "article-system.jfif"
---

The `<article>` component in **deveb.css** leverages native semantic HTML5 to create modular, self-contained content blocks. Without relying on heavy utility classes or JavaScript triggers, it provides an elegant structure for blog posts, news items, cards, and editorial content.

---

## Key Features

- **Purely Semantic:** Applies styles directly to `<article>` and its native children (`<header>`, `<section>`, `<footer>`, `<h1>`-`<h6>`, `<time>`, `<figure>`).
- **Zero JavaScript:** Responsive states and layout shifts rely entirely on modern CSS features.
- **Card & Feed Ready:** Functions seamlessly inside grid systems, flexible columns, or standalone reading views.
- **Fluid Typography & Spacing:** Internal padding and typographic hierarchy adapt automatically across viewports.

---

## Basic Usage

To build a standard article card or blog post entry, wrap your content inside a native `<article>` tag.

```html
<article>
  <header>
    <span>Sep 16, 2026</span>
    <h2>Building Light Websites with Pure CSS</h2>
  </header>
  
  <section>
    <p>
      Discover how stripping away JavaScript frameworks allows modern CSS to handle structural layouts, responsive typography, and state management effortlessly.
    </p>
  </section>

  <footer>
    <a href="#">Read full article &rarr;</a>
  </footer>
</article>
```

---

## Anatomy of an Article

When using `deveb.css`, the `<article>` tag structures its immediate child elements automatically:

1. **`<header>`**: Contains meta information such as dates, category badges, author details, and the main title (`<h2>` or `<h3>`).
2. **`<section>` or `<p>`**: The body content area. It handles line-height optimization, max-width constraints for readability, and link styling.
3. **`<footer>`**: Positioned at the bottom of the card or post. Ideal for tags, social shares, "Read More" links, or author signatures.

---

## Grid Integration

Articles are designed to work naturally with the `deveb.css` grid layout. When placed inside a grid container, every `<article>` stretches uniformly and maintains internal vertical rhythm.

```html
<div class="grid">
  <article>
    <header>
      <h2>First Entry</h2>
    </header>
    <section>
      <p>Content for the first column.</p>
    </section>
  </article>

  <article>
    <header>
      <h2>Second Entry</h2>
    </header>
    <section>
      <p>Content for the second column.</p>
    </section>
  </article>
</div>
```

---

## Media & Figures inside `<article>`

Adding visual media like images or code snippets within an article retains proportional scaling without breaking layout boundaries.

```html
<article>
  <figure>
    <img src="/assets/img/article-banner.jpg" alt="Article Illustration">
  </figure>
  <header>
    <h2>Visual Content Layout</h2>
  </header>
  <section>
    <p>Images inside figures within an article automatically fill the top or inline width with crisp border-radius alignment.</p>
  </section>
</article>
```

---

## Best Practices

- **Keep it Self-Contained:** An `<article>` should make sense on its own if syndicated or rendered outside the main page flow.
- **Use Native Headings:** Maintain proper heading hierarchy (`<h2>` or `<h3>` inside cards) to keep accessibility and document outlines clean.
- **Avoid Utility Bloat:** Do not add extra class names unless custom theme overrides are required—`deveb.css` styles the native tags directly.