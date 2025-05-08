---
layout: page
title: Latest Event
permalink: /event/
position: 7
---

<iframe src="https://calendar.google.com/calendar/embed?src=e5437755aa56250df01f979fd86e6617caedcc076d427bd5a1b004e30bdc48dd%40group.calendar.google.com&ctz=Asia%2FShanghai" 
        style="border: 0" 
        width="100%" 
        height="600" 
        frameborder="0" 
        scrolling="no"></iframe>
<!-- <iframe src="https://calendar.google.com/calendar/embed?src=e5437755aa56250df01f979fd86e6617caedcc076d427bd5a1b004e30bdc48dd%40group.calendar.google.com&ctz=Asia%2FShanghai" style="border: 0" width="800" height="600" frameborder="0" scrolling="no"></iframe> -->

<div class="post-cards">
  {% for post in site.posts %}
    <div class="post-card">
      <!-- Post Content -->
      <div class="post-card-content">
        <h2 class="post-card-title">
          <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
        <!-- <p class="post-card-excerpt">
          {{ post.excerpt | strip_html | truncatewords: 20 }}
        </p> -->
        <p class="post-card-meta"> {{ post.date | date: "%B %d, %Y" }}</p>
      </div>

      <!-- Feature Image (Square on the right) -->
      {% if post.img %}
        <div class="post-card-image" style="background-image: url('{{ post.img | prepend: site.baseurl }}');"></div>
      {% endif %}
    </div>
  {% endfor %}
</div>

<!-- Pagination (if applicable) -->
{% if paginator.pages.size > 1 %}
  <div class="pagination">
    <span class="previous">
      {% if paginator.previous_page %}
        <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}">&laquo; Previous</a>
      {% else %}
        <span class="disabled">&laquo; Previous</span>
      {% endif %}
    </span>
    <span class="next">
      {% if paginator.next_page %}
        <a href="{{ paginator.next_page_path | prepend: site.baseurl }}">Next &raquo;</a>
      {% else %}
        <span class="disabled">Next &raquo;</span>
      {% endif %}
    </span>
  </div>
{% endif %}
