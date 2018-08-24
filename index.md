---
layout: default
---

# Header 1

Text can be **bold**, _italic_, or ~~strikethrough~~.

## Program

### Ruby

<ul>
  {% for post in site.categories.ruby %}
    <li>
      <a href="{{ post.url | absolute_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>