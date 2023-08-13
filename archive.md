---
layout: post
title: Archive
permalink: /archive/
---

This list of blog posts used to be on the main page. I've started writing on so I purposed the main page to be an introduction. This is the archive of those blog posts.
This is also for old longer, personal updates. :)

<section class="post-list">
  <div class="container">
    {% for post in site.posts %}
      {% unless post.next %}
        <h2 class="category-title">{{ post.date | date: '%Y' }}</h2>
      {% else %}
        {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
        {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
        {% if year != nyear %}
          <h2 class="category-title">{{ post.date | date: '%Y' }}</h2>
        {% endif %}
      {% endunless %}
      <article class="post-item">
        <span class="post-meta date-label">{{ post.date | date: "%b %d" }}</span>
        <div class="article-title"><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></div>
      </article>
    {% endfor %}
  </div>
</section>
