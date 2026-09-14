---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Hoş Geldiniz

Deveb.css ve No JS Forever felsefesiyle hazırladığımız tüm içerikler aşağıda listelenmiştir.

<div class="home-content">

  <!-- 1. DOKÜMANLAR BÖLÜMÜ -->
  <section class="docs-section">
    <h2>Dokümanlar</h2>
    <ul class="doc-list">
      <!-- site.docs koleksiyonundaki tüm belgeleri listeler -->
      {% for doc in site.docs %}
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
  <section class="posts-section">
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