---
layout: default
---

## A Little Faith

- [Don't Panic!](https://coolaj86.com/articles/dont-panic.html)
- [Tools](./pages/tools.html) 


***

## Code

### python

- [Data fit](./pages/python-fit.html)

### MD

<ul>
  {% for post in site.categories.md %}
    <li>
      <a href="{{ post.url | remove_first:'/' }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

### Javascript

[JS Animation Libraries](https://dashbouquet.com/blog/frontend-development/10-javascript-animation-libraries-to-follow-in-2018)

- [Three JS](https://github.com/mrdoob/three.js)
- [D3.js(Data Visualization)](https://d3js.org/)

***

## AI

[companies](./pages/ai-companies.html)

### Cloud

- [AutoML](https://cloud.google.com/automl/)
- [阿里云PAI](https://data.aliyun.com/product/learn)

### TensorFlow

<ul>
  {% for post in site.categories.tensorflow %}
    <li>
      <a href="{{ post.url | remove_first:'/' }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

***

## Server

- [まとめ(Qiita)](https://qiita.com/you8/items/670bfa6573cec2494c96)

***

## School
- Coursera
- Udemy
- ドットインストール

[memo](./pages/memo.html)

[three.js practice](./pages/three.html)

***

Update: 2018-08-25