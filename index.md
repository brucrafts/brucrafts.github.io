---
layout: default
title: início
---

<section class="hero">
  <h1><span class="heart">♡</span> brucrafts <span class="heart">♡</span></h1>
  <p class="tagline">alguns games e muitos hobbies de jovem senhora</p>
  <p class="intro-copy">Receitas, gráficos, projetos e pequenas inspirações<br class="desktop-only"> para fazer algo seu também. ♡</p>
  <div class="pixel-decor" role="img" aria-label="games, crafts, bordado e livros">
    <span title="games">🎮</span><b>✦</b><span title="crochê">🧶</span><b>✦</b><span title="bordado">🪡</span><b>✦</b><span title="livros">📚</span>
  </div>
</section>

<div class="separator"><span>♡</span></div>

<section class="feed-section">
  <div class="section-title">
    <h2><span class="sparkle">✧</span> feed</h2>
    <p>meus últimos posts por aqui</p>
  </div>

  {% assign latest_posts = site.posts | sort: "date" | reverse %}
  {% for post in latest_posts limit: 5 %}
    <article class="feed-card">
      {% if post.image %}
        <a class="feed-photo" href="{{ post.url | relative_url }}" aria-label="Ver {{ post.title }}">
          <img src="{{ post.image | relative_url }}" alt="{{ post.image_alt | default: post.title | escape }}" loading="lazy" decoding="async">
        </a>
      {% endif %}
      <div class="feed-content">
        <div class="post-label"><span>✿</span> {{ post.label | default: "new post" }}</div>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p class="post-excerpt">{{ post.excerpt_text | default: post.description }}</p>
        <div class="post-meta">{{ post.category }}{% if post.date %} <span>·</span> {{ post.date | date: "%d.%m.%Y" }}{% endif %}</div>
        <a class="text-button" href="{{ post.url | relative_url }}">ver post <span>→</span></a>
      </div>
      <span class="corner-symbol" aria-hidden="true">♡</span>
    </article>
  {% endfor %}

  {% if site.posts.size == 0 %}
    <div class="empty-feed">
      <p>♡ em breve, novidades do meu craft room!</p>
      <small>Adicione posts na pasta <code>_posts</code> para preencher o feed.</small>
    </div>
  {% endif %}
</section>

<div class="bottom-decor"><span>✿</span><div></div><b>&lt;/♥&gt;</b><div></div><span>✿</span></div>
