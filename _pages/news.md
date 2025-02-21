---
layout: default
title: All News
permalink: /news/
---

<h1>All News</h1>

<div class="news">
  {% if site.news != blank %}
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
        {% assign news = site.news | reverse %}
        {% assign news_limit = site.news | size %}
        
        {% for item in news limit: news_limit %}
          <tr>
            <th scope="row" style="width: 20%">{{ item.date | date: '%b %Y' }}</th>
            <td>
              {% if item.inline %}
                {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
              {% else %}
                <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
              {% endif %}
            </td>
          </tr>
        {% endfor %}
      </table>
    </div>
  {% else %}
    <p>No news so far...</p>
  {% endif %}
</div>
