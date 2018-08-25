---
layout: default
title:  "GPU version setup"
date:   2018-08-25 15:30:00 +0800
categories: tensorflow
---

# Environment

- Win7
- Python 3.6.6
- CUDA 9.0
- TensorFlow-gpu 1.10.0
- cudnn 9.0

## install

`pip3 install --upgrade tensorflow-gpu`

## run

```python
import tensorflow as tf
```

## error

![error-tf]({{site.url}}/images/error-tf.png)

**ok after uninstall tensorflow cpu version(?)**

`pip3 uninstall tensorflow`

## Ref.

- [win10+cuda9.0+cuDNN 7.0+Tensorflow1.5（GPU）安装](https://blog.csdn.net/zw__chen/article/details/79374467)

