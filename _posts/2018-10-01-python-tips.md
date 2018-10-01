---
layout: default
title:  "Python tips"
date:   2018-10-01 21:30:00 +0800
categories: python
---

## 二维数组赋值
```python
matrix = [[0] * 3] * 3
```
→赋值时整列变成同一数值
改为
```python
matrix = [([0] * 3) for i in range(3)]
```

### Ref.
- [csdn](https://blog.csdn.net/shidamowang/article/details/80091372)