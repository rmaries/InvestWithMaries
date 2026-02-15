---
layout: page
title: Insights & Blog
permalink: /blog/
---

Stay updated with the latest trends in mutual funds, market insights, and financial planning tips.

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </li>
  {% endfor %}
</ul>

{% if site.paginate %}
  <div class="pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}" class="previous">
        &laquo; Previous
      </a>
    {% endif %}
    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}" class="next">Next &raquo;</a>
    {% endif %}
  </div>
{% endif %}
