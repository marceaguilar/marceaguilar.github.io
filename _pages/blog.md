---
layout: default
permalink: /blog/
title: blog/media
nav: true
nav_order: 1
pagination:
  enabled: false
---

<div class="post">

{% assign blog_name_size = site.blog_name | size %}
{% assign blog_description_size = site.blog_description | size %}

{% if blog_name_size > 0 or blog_description_size > 0 %}

  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>
{% endif %}

{% if site.display_tags or site.display_categories %}

  <div class="tag-category-list">
    <ul class="p-0 m-0">
      {% for tag in site.display_tags %}
        <li>
          <i class="fa-solid fa-hashtag fa-sm"></i> <a href="{{ tag | slugify | prepend: '/blog/tag/' | relative_url }}">{{ tag }}</a>
        </li>
        {% unless forloop.last %}<p>&bull;</p>{% endunless %}
      {% endfor %}
      {% if site.display_categories.size > 0 and site.display_tags.size > 0 %}
        <p>&bull;</p>
      {% endif %}
      {% for category in site.display_categories %}
        <li>
          <i class="fa-solid fa-tag fa-sm"></i> <a href="{{ category | slugify | prepend: '/blog/category/' | relative_url }}">{{ category }}</a>
        </li>
        {% unless forloop.last %}<p>&bull;</p>{% endunless %}
      {% endfor %}
    </ul>
  </div>
{% endif %}

{% assign featured_posts = site.posts | where: "featured", "true" %}
{% if featured_posts.size > 0 %}
<br>

  <div class="container featured-posts">
    {% assign is_even = featured_posts.size | modulo: 2 %}
    <div class="row row-cols-{% if featured_posts.size <= 2 or is_even == 0 %}2{% else %}3{% endif %}">
      {% for post in featured_posts %}
        <div class="col mb-4">
          <a href="{{ post.url | relative_url }}">
            <div class="card hoverable">
              <div class="row g-0">
                <div class="col-md-12">
                  <div class="card-body">
                    <div class="float-right">
                      <i class="fa-solid fa-thumbtack fa-xs"></i>
                    </div>
                    <h3 class="card-title text-lowercase">{{ post.title }}</h3>
                    <p class="card-text">{{ post.description }}</p>

                    {% if post.external_source == blank %}
                      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
                    {% else %}
                      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
                    {% endif %}
                    {% assign year = post.date | date: "%Y" %}

                    <p class="post-meta">
                      {{ read_time }} min read &nbsp; &middot; &nbsp;
                      <a href="{{ year | prepend: '/blog/' | prepend: site.baseurl }}">
                        <i class="fa-solid fa-calendar fa-sm"></i> {{ year }} </a>
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </a>
        </div>
      {% endfor %}
    </div>

  </div>
  <hr>
{% endif %}

{% assign personal_count = site.posts | where_exp: "p", "p.external_source == nil" | size %}
{% assign external_count = site.posts | where_exp: "p", "p.external_source" | size %}
{% assign total_count = site.posts | size %}

<div class="post-filter" role="tablist" aria-label="Filter posts">
  <button type="button" class="post-filter__chip is-active" data-filter="all" role="tab" aria-selected="true">
    <i class="fa-solid fa-layer-group"></i> All
    <span class="post-filter__count">{{ total_count }}</span>
  </button>
  <button type="button" class="post-filter__chip" data-filter="personal" role="tab" aria-selected="false">
    <i class="fa-solid fa-hashtag"></i> Personal
    <span class="post-filter__count">{{ personal_count }}</span>
  </button>
  <button type="button" class="post-filter__chip" data-filter="external" role="tab" aria-selected="false">
    <i class="fa-solid fa-hashtag"></i> External
    <span class="post-filter__count">{{ external_count }}</span>
  </button>
</div>

<ul class="post-list" id="blog-post-list">
  {% for post in site.posts %}
    {% assign is_external = false %}
    {% if post.external_source %}{% assign is_external = true %}{% endif %}
    {% include post_card.liquid post=post is_external=is_external %}
  {% endfor %}
</ul>

<p class="post-filter__empty" hidden>No posts match this filter.</p>

<script>
  (function () {
    const chips = document.querySelectorAll('.post-filter__chip');
    const items = document.querySelectorAll('#blog-post-list .post-list-item');
    const emptyMsg = document.querySelector('.post-filter__empty');
    const list = document.getElementById('blog-post-list');

    function applyFilter(filter) {
      let visible = 0;
      items.forEach((el) => {
        const type = el.getAttribute('data-post-type');
        const show = filter === 'all' || type === filter;
        el.hidden = !show;
        if (show) visible += 1;
      });
      if (emptyMsg) emptyMsg.hidden = visible !== 0;
      if (list) list.hidden = visible === 0;
    }

    chips.forEach((chip) => {
      chip.addEventListener('click', () => {
        chips.forEach((c) => {
          c.classList.remove('is-active');
          c.setAttribute('aria-selected', 'false');
        });
        chip.classList.add('is-active');
        chip.setAttribute('aria-selected', 'true');
        applyFilter(chip.getAttribute('data-filter'));
      });
    });
  })();
</script>

</div>
