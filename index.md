---
layout: default
---

## A Little Faith

- [Don't Panic!](https://coolaj86.com/articles/dont-panic.html)

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

[companies](./pages/ai-companies.html)

### TensorFlow

<ul>
  {% for post in site.categories.tensorflow %}
    <li>
      <a href="{{ post.url | remove_first:'/' }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

***

Update: 2018-08-25