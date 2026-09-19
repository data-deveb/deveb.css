---
layout: doc
title: "Article System"
description: Self-contained, semantic layout structure powered
categories: ["Getting Started"]
permalink: /docs/article/
nav_order: 2
tags: ["Block", "Article", "UX Design", "Semantic HTML", "Layout"]
banner-image: "article-system.jfif"
---

The `<article>` component in **deveb.css** leverages native semantic HTML5 to create modular, self-contained and machine-readable content blocks. Built with a **No-JS, Zero-Build, and Pure-CSS** architecture, it transforms standard HTML markup into elegant cards, editorial posts, and feed elements while preserving semantic purity.

---

## Why Native `<article>` Matters in the AI Era

In the evolving web landscape, code is no longer read only by human eyes and web browsers—it is continuously parsed by **Large Language Models (LLMs), AI Agents, RAG (Retrieval-Augmented Generation) crawlers, and assistive technologies**.

According to the **W3C Specification** and **MDN Web Docs**, the `<article>` element represents a complete, self-contained composition that is intended to be **independently distributable or reusable** (e.g., in RSS syndication, social previews, or AI search summaries).

### The Golden Rule of `<article>`

> _"If you strip this content block away from the page and place it on another platform (like an RSS reader, an AI agent digest, or an external feed), does it still make total sense on its own?"_
> 
> If the answer is **yes**, it MUST be an `<article>`—not a `<div class="card">`.
> 

---

### Key Benefits:

1.  **AI & Generative Engine Optimization (GEO):** LLM crawlers isolate `<article>` tags to extract authoritative, context-complete answers. Replacing `<div>` soup with `<article>` ensures AI agents digest your content accurately without losing structural context.
    
      
    
2.  **Accessibility (A11y) & ARIA:** Screen readers automatically map `<article>` to the implicit `article` ARIA landmark, allowing users with visual impairments to jump directly between content items using keyboard navigation.
    
      
    
3.  **Syndication Ready:** Modern browser Reader Modes and content aggregators rely on `<article>` boundaries to strip out layout noise (ads, sidebars) and present pure content.


## The deveb.css Approach

Traditional frameworks force developers to write utility bloat like `<div class="card card-body shadow-sm p-4 flex flex-col">`. **deveb.css** eliminates class dependency entirely. It targets native HTML elements directly within the `<article>` subtree.

  

```
+-------------------------------------------------------+
|  <article>                                            |
|   +-------------------------------------------------+ |
|   | <header> Meta info, <time>, <h2> title          | |
|   +-------------------------------------------------+ |
|   | <section> Main body content, paragraphs         | |
|   +-------------------------------------------------+ |
|   | <footer> Author bio, tags, action links         | |
|   +-------------------------------------------------+ |
+-------------------------------------------------------+
```
---

## Key Features

-   **100% Pure Semantic CSS:** Styles apply directly to native `<article>` elements and their structural children (`<header>`, `<section>`, `<footer>`, `<h2>`, `<time>`, `<figure>`).
-   **Zero JavaScript Dependency:** Fluid responsive shifts, line-height calculations, and spatial rhythm rely strictly on modern CSS features.
- **Card & Feed Ready:** Functions seamlessly inside grid systems, flexible columns, or standalone reading views.
-   **Fluid Layout Rhythm:** Internal padding and typographic scale adapt automatically across all viewports without media-query bloat.
-   **Native Nesting Support:** Supports sub-articles (e.g., user comments nested within a main post) per standard HTML5 specifications.

---

## Basic Usage

To build a standard card or blog post entry, wrap your content inside a native `<article>` tag using appropriate semantic children.

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

When using **deveb.css**, structural elements within an `<article>` carry explicit roles:

1.  **`<header>`**: Houses meta information such as publication dates (`<time datetime="...">`), category badges, and the primary entry title (`<h2>` or `<h3>`). _(MDN Recommendation: Every `<article>` should ideally contain at least one heading element)._
2.  **`<section>` or `<p>`**: The main body content area. Handles optimal line length (`ch` units) for effortless readability and applies clean inline styling to links and text formatting.
3.  **`<footer>`**: Positioned at the bottom of the card or post. Perfect for social sharing triggers, author signatures, action links, or taxonomy tags.

## Advanced: Nesting Articles (W3C Pattern)

According to the W3C specification, an `<article>` can be nested within another `<article>` if the inner content is directly related to the parent context. The most common use case is a **blog post with user comments**.

```HTML
<!-- Main Blog Post Article -->
<article>
  <header>
    <h2>Understanding Zero-JS Frameworks</h2>
    <p>By <strong>Alex Developer</strong></p>
  </header>
  
  <section>
    <p>Pure CSS frameworks offer unprecedented performance improvements...</p>
  </section>

  <!-- Nested Article: User Comments Section -->
  <section class="comments">
    <h3>Community Responses</h3>

    <article>
      <header>
        <strong>Jane Doe</strong> 
        <time datetime="2027-03-16">10 mins ago</time>
      </header>
      <section>
        <p>Great write-up! Moving away from JS build pipelines changed my workflow entirely.</p>
      </section>
    </article>
  </section>
</article>

```

---

## Grid Integration

Articles are designed to work naturally inside the **deveb.css** grid layout system. When placed inside a grid container, every `<article>` stretches uniformly, aligns its internal `<footer>` to the bottom automatically, and maintains equal vertical height across columns.

```html
<div class="grid">
  <article>
    <header>
      <h2>First Entry</h2>
    </header>
    <section>
      <p>Content for the first column entry.</p>
    </section>
    <footer><a href="#">Read More</a></footer>
  </article>

  <article>
    <header>
      <h2>Second Entry</h2>
    </header>
    <section>
      <p>Content for the second column entry.</p>
    </section>
    <footer><a href="#">Read More</a></footer>
  </article>
</div>
```

---

## Media & Figures inside `<article>`

Visual media like images, videos, or code blocks wrapped inside `<figure>` retain crisp proportion scaling, rounded borders, and vertical alignment without breaking layout boundaries.

```html
<article>
  <figure>
    <img src="/assets/img/article-banner.jpg" alt="Minimalist Web Architecture">
    <figcaption>Figure 1: Lightweight architecture overview.</figcaption>
  </figure>
  
  <header>
    <h2>Visual Content Layout</h2>
  </header>
  
  <section>
    <p>
      Media elements placed inside an article automatically align to the top border and scale fluidly based on the parent card width.
    </p>
  </section>
</article>
```

---

## Best Practices (W3C & deveb.css)

-   **Must Be Standalone:** Ensure the article content conveys full meaning when read out of context in an RSS aggregator or AI search summary.
-   **Use `<time>` with `datetime`:** Always format dates using `<time datetime="YYYY-MM-DD">` inside the header. This allows search engines and calendar agents to parse exact timestamps.
- **Keep it Self-Contained:** An `<article>` should make sense on its own if syndicated or rendered outside the main page flow.
-   **Maintain Heading Hierarchy:** Use appropriate heading levels (`<h2>` or `<h3>` inside cards) to keep document outlines clean for SEO and assistive readers.
-   **Avoid Utility Class Bloat:** Let `deveb.css` style native elements directly. Avoid adding cluttering utility classes unless custom theme overrides are required.


---

## Advanced Features & Best Practices

### AI & RAG Engine Optimization (GEO)
Modern search engines and Large Language Models (LLMs) prioritize structured, semantically clear content. By utilizing native `<article>` elements with explicit child structures instead of class-heavy `<div>` containers, your content becomes effortlessly parseable by AI crawlers and RAG (Retrieval-Augmented Generation) systems.

* **Machine-Readable Structure:** Clearly demarcates entry metadata, main narrative, and actionable footers.
* **Context Preservation:** Ensures that content extracted out of context retains its semantic integrity in automated summaries and AI search results.


---

### Structured Data & Schema.org Integration

You can enrich your `<article>` tags with Schema.org microdata without breaking any **deveb.css** layouts. Combining native HTML5 semantics with structured metadata provides maximum visibility for search engines:

```html
<article itemscope itemtype="[https://schema.org/TechArticle](https://schema.org/TechArticle)">
  <header>
    <time datetime="2027-03-15" itemprop="datePublished">March 15, 2027</time>
    <h2 itemprop="headline">Building Light Websites with Pure CSS</h2>
  </header>
  
  <section itemprop="articleBody">
    <p>
      Discover how stripping away JavaScript frameworks allows modern CSS to handle structural layouts effortlessly.
    </p>
  </section>

  <footer>
    <span itemprop="author" itemscope itemtype="[https://schema.org/Person](https://schema.org/Person)">
      Written by <span itemprop="name">Jane Doe</span>
    </span>
  </footer>
</article>
```

## Best Practices Checklist
- **Ensure Standalone Independence:** Verify that the article content remains fully understandable when isolated in an RSS reader or AI digest.

- **Always Use Explicit Timestamps:** Use <time datetime="YYYY-MM-DD"> inside headers to ensure date parsing accuracy for search engines and calendar agents.

- **Maintain Logical Heading Rhythms:** Keep heading hierarchies consistent (<h2> or <h3> inside card elements) to preserve clean accessibility trees for screen readers.

- **Avoid Utility Class Bloat:** Rely on deveb.css native element styling—avoid adding unnecessary utility classes unless custom structural overrides are required.