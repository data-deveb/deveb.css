---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="hero flex" xs="(1/1)">
  <div class="flex right center" xs="(1/1)" md="(1/2)">
    <article>
      <h1>No JS & No Rebuild! Forever Only CSS</h1>
      <h2>Create web pages with deveb.css</h2>
      <p>The days of loading a JavaScript bundle for every interaction are over. This approach, which pushes the boundaries of CSS, allows you to build modern websites with pure CSS—without the need for complex state management or bloated libraries.</p>
      <p>Pages load faster, server load is reduced, and users enjoy a seamless experience. Because sometimes, the best code is the code that’s never been written (or hasn’t been tainted by JS).</p>
      <a class="glow-on-hover" href ="./assets/css/deveb.css" download="deveb.css">Download Now</a>
    </article>
  </div>
  <div class="flex right center" xs="(1/1)" md="(1/2)">
    <div class="center">
      <img src="./assets/img/hero_deveb.css.png">
    </div>
  </div>
</div>
<!-- <div>
<pre class="highlight"><code><span class="nt">&lt;link </span><span class="na">rel=</span><span class="s">"stylesheet" </span><span class="na">href=</span><span class="s">"/assets/css/deveb.css" </span>mode=<span class="s">"flex"</span><span class="nt">&gt;</span></code></pre>
</div> -->
<div class="home-content">
    
  <!-- 1. DOKÜMANLAR BÖLÜMÜ -->
  {% assign sorted_docs = site.docs | sort: 'nav_order' %}
  <section class="docs-section" xs="(1/1)">
    <h2>Documention</h2>
    <ul class="doc-list">
      <!-- site.docs koleksiyonundaki tüm belgeleri listeler -->
      {% for doc in sorted_docs %}
        <li>
          <div class="c6">
            <div>
            <div class="c6-top">
              <div class="c6-share" style="">
                <svg viewBox="0 0 24 24" width="14" height="14" fill="none" stroke="#1a1a1a" stroke-width="1.8"><path d="M12 15V4M7 8l5-5 5 5M5 15v4a1 1 0 001 1h12a1 1 0 001-1v-4"></path></svg>
              </div>
              <div class="c6-img">
                <a href="{{ doc.url | relative_url }}"><img src="./assets/img/{{ doc.banner-image }}"></a>
              </div>    
            </div>
            <div class="c6-name"><a href="{{ doc.url | relative_url }}">{{ doc.title }}</a></div>
            <div class="c6-role">{{ doc.categories[0] }}</div>
            <div class="c6-tags">
            {% if doc.tags %}              
              {% for tag in doc.tags limit: 3 %}
              <div class="c6-tag">
                {{ tag }}
              </div>
              {% endfor %}              
            {% endif %}
            </div>
            <div class="c6-desc">
              {% if doc.description %}
                <p>{{ doc.description }}</p>
              {% endif %}
            </div>
            <span></span>
            </div>
            <div class="c6-actions">
              <div class="c6-cta center">
                <a href="{{ doc.url | relative_url }}">Get in read</a>
              </div>
              <div class="c6-bookmark">
                <svg viewBox="0 0 24 24" width="15" height="15" fill="none" stroke="#1a1a1a" stroke-width="1.8"><path d="M6 3h12v18l-6-4-6 4z"></path></svg>
              </div>
            </div>
          </div>
                
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