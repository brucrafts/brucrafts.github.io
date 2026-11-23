---
layout: default
title: home
permalink: /en/
lang: en
alternate_url: /
description: Some games and lots of old-lady hobbies.
---

<section class="hero">
  <h1><span class="heart">♡</span> brucrafts <span class="heart">♡</span></h1>
  <p class="tagline">some games and lots of old-lady hobbies</p>
  <p class="intro-copy">Patterns, charts, projects, and little inspiration<br class="desktop-only"> to make something of your own. ♡</p>
  <div class="pixel-decor" role="img" aria-label="Games, crafts, embroidery, and books">
    <span title="games">🎮</span><b>✦</b><span title="crochet">🧶</span><b>✦</b><span title="embroidery">🪡</span><b>✦</b><span title="books">📚</span>
  </div>
</section>

<div class="separator"><span>♡</span></div>

<section class="feed-section">
  <div class="section-title">
    <h2><span class="sparkle">✧</span> feed</h2>
    <p>my latest posts</p>
  </div>

  {% assign latest_posts = site.posts | where: "lang", page.lang | sort: "date" | reverse %}
  {% for post in latest_posts limit: 5 %}
    <article class="feed-card">
      {% if post.image %}
        <a class="feed-photo" href="{{ post.url | relative_url }}" aria-label="View {{ post.title | escape }}">
          <img src="{{ post.image | relative_url }}" alt="{{ post.image_alt | default: post.title | escape }}" loading="lazy" decoding="async">
        </a>
      {% endif %}
      <div class="feed-content">
        <div class="post-label"><span>✿</span> {{ post.label | default: "new post" }}</div>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p class="post-excerpt">{{ post.excerpt_text | default: post.description }}</p>
        <div class="post-meta">{{ post.category }}{% if post.date %} <span>·</span> {{ post.date | date: "%m/%d/%Y" }}{% endif %}</div>
        <a class="text-button" href="{{ post.url | relative_url }}">read post <span>→</span></a>
      </div>
      <span class="corner-symbol" aria-hidden="true">♡</span>
    </article>
  {% endfor %}

  {% if latest_posts.size == 0 %}
    <div class="empty-feed">
      <p>♡ new crafts coming soon!</p>
      <small>Add posts to the <code>_posts</code> folder to fill the feed.</small>
    </div>
  {% endif %}
</section>

<div class="bottom-decor"><span>✿</span><div></div><b>&lt;/♥&gt;</b><div></div><span>✿</span></div>
