---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="hero">
<div class="(1/1) right center" md="(1/2)">
    <div>
        <h1>No JS Forever Pure CSS</h1>
        <p>The days of loading a JavaScript bundle for every interaction are over. This approach, which pushes the boundaries of CSS, allows you to build modern websites with pure CSS—without the need for complex state management or bloated libraries.</p>
        <p>Pages load faster, server load is reduced, and users enjoy a seamless experience. Because sometimes, the best code is the code that’s never been written (or hasn’t been tainted by JS).</p>
    </div>
</div>
<div class="(1/1) center" md="(1/2)">
    <div class="center" style="border: 1px dashed rgb(197, 198, 230); padding: 10px; margin:10px;">
        <img src="./assets/img/hero_deveb.css.png">
    </div>
</div>
</div>

<div class="home-content">
    
  <!-- 1. DOKÜMANLAR BÖLÜMÜ -->
  {% assign sorted_docs = site.docs | sort: 'nav_order' %}
  <section class="(1/1) docs-section">
    <h2>Documention</h2>
    <ul class="doc-list">
      <!-- site.docs koleksiyonundaki tüm belgeleri listeler -->
      {% for doc in sorted_docs %}
        <li>
          <a href="{{ doc.url | relative_url }}">{{ doc.title }}</a>
          {% if doc.description %}
            <p>{{ doc.description }}</p>
          {% endif %}
        </li>
      {% endfor %}
    </ul>
  </section>

  <hr style="margin: 40px 0; border: 0; border-top: 1px solid #eaeaea;">

  <!-- 2. BLOG YAZILARI BÖLÜMÜ -->
  <section class="(1/1) posts-section">
    <h2>Son Yazılar</h2>
    <ul class="post-list">
      <!-- site.posts koleksiyonundaki tüm yazıları kronolojik sırayla listeler -->
      {% for post in site.posts %}
        <li>
          <span class="post-meta">{{ post.date | date: "%b %d, %Y" }}</span>
          <h3>
            <a class="post-link" href="{{ post.url | relative_url }}">
              {{ post.title }}
            </a>
          </h3>
          {% if post.excerpt %}
            {{ post.excerpt }}
          {% endif %}
        </li>
      {% endfor %}
    </ul>
  </section>

</div>