---
layout: default
---

## A Little Faith

Text can be **bold**, _italic_, or ~~strikethrough~~.

***

## Code

### MD

<ul>
  {% for post in site.categories.md %}
    <li>
      <a href="{{ post.url | remove_first:'/' }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

***

## AI

### Tensorflow

<ul>
  {% for post in site.categories.tensorflow %}
    <li>
      <a href="{{ post.url | remove_first:'/' }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

***

## Skill Set

***

Update: 2018-08-24