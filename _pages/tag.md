---
layout: archive
permalink: /tag/
title: "Themenseite"
excerpt: "Hier findest du eine Übersicht aller Beiträge nach Themen geordnet."
---

Diese Seite enthält {{ site.posts | size }} Beiträge und {{ site.tags | size }} Themen.

<div class="entries__columns">
  <h2 class="title">Browse by topic</h2>
  <ul>
    {% assign sorted_tags = site.tags | sort_tags_by_name %}
    {% for tag in sorted_tags %}
      <li>
        <a href="/tag/{{ tag[0] | replace:' ','-' | downcase }}/">
          <strong>{{ tag[0] }}</strong> <span class="count">{{ tag[1] }}</span>
        </a>
      </li>
    {% endfor %}
  </ul>
</div>
