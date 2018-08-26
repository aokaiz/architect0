---
layout: default
title:  "GPU version setup"
date:   2018-08-25 17:30:00 +0800
categories: tensorflow
---

# Environment

- Win7
- Python 3.6.6
- CUDA 9.0
- TensorFlow-gpu 1.10.0
- cudnn 9.0 v7.2.1

## install

`pip3 install --upgrade tensorflow-gpu`

## run

```python
import tensorflow as tf
```

## error

### AVX problem

![error-tf]({{site.url}}/images/error-tf.png)

[stackoverflow post](https://stackoverflow.com/questions/51912155/tensorflow-importerror-dll-load-failed-with-error-code-1073741795)

```
pip3 uninstall tensorflow-gpu
pip3 install tensorflow-gpu==1.5
```
OK

### cudnn version

![error-cudnn]({{site.url}}/images/error-cudnn.png)

[github post](https://github.com/tensorflow/tensorflow/issues/16479)

>it looks like TensorFlow 1.5.0 is built with `CUDA_VERSION 9.0.176` `CUDNN_VERSION 7.0.5.15`

```
uninstall cudnn 9.0 v7.2.1
install cudnn 9.0 v7.0.5
```
OK

## tensorboard

`pip3 install tensorboard`

## test

GPU is ~5 times faster than CPU version(`GTX750Ti` and `Xeon X5675`)

## seq2seq

>After update to 1.0.0 and above, they change the location of seq2seq from tf.nn.seq2seq to tf.contrib.legacy_seq2seq

[github issue](https://github.com/suriyadeepan/easy_seq2seq/issues/39)

replace `tf.nn.seq2seq` by `tf.contrib.legacy_seq2seq`

## Ref.

- [win10+cuda9.0+cuDNN 7.0+Tensorflow1.5（GPU）安装](https://blog.csdn.net/zw__chen/article/details/79374467)

