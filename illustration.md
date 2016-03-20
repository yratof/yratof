---
layout: portfolio
title: illustration
permalink: /illustration/
---

 <ul class="post-list">
    {% for post in site.illustration %}
      <li>
          <span class="post-meta"><small>
            <!-- Whitespace added for readability -->
            {% assign d = post.date | date: "%-d" %}
            {% assign m = post.date | date: "%B" %}

            {% case m %}
              {% when 'April' or 'May' or 'June' or 'July' %}{{ m }}
              {% when 'September' %}Sept.
              {% else %}{{ post.date | date: "%b" }}.
              {% endcase %}
            {% case d %}
              {% when '1' or '21' or '31' %}{{ d }}st
              {% when '2' or '22' %}{{ d }}nd
              {% when '3' or '23' %}{{ d }}rd
              {% else %}{{ d }}th
              {% endcase %},
            {{ post.date | date: "%Y" }}
          </small>
          </span>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>
