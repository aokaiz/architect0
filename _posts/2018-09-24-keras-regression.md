---
layout: default
title:  "Keras Regression"
date:   2018-09-24 17:30:00 +0800
categories: tensorflow
---

## Read data
```python
import pandas as pd

CSV_COLUMN_NAMES = ['A', 'B',
                    'C', 'Y']

def load_data(y_name='Y'):
  print('load data...')
  train_path = 'test.csv'
  test_path = 'test2.csv'
  train = pd.read_csv(train_path, names=CSV_COLUMN_NAMES, header=0)
  train_x, train_y = train, train.pop(y_name)
  test = pd.read_csv(test_path, names=CSV_COLUMN_NAMES, header=0)
  test_x, test_y = test, test.pop(y_name)
```
## Regression
```python
from __future__ import absolute_import, division, print_function

import tensorflow as tf
from tensorflow import keras

import numpy as np

import data

print(tf.__version__)

(train_x, train_y), (test_x, test_y)= data.load_data()

print(train_x[1])

mean = train_x.mean(axis=0)
std = train_x.std(axis=0)
train_x = (train_x - mean) / std
test_x = (test_x - mean) / std

print(train_x[0])  # First training sample, normalized

def build_model():
  model = keras.Sequential([
    keras.layers.Dense(64, activation=tf.nn.relu,
                       input_shape=(train_x.shape[1],)),
    keras.layers.Dense(64, activation=tf.nn.relu),
    keras.layers.Dense(1)
  ])

  optimizer = tf.train.RMSPropOptimizer(0.001)

  model.compile(loss='mse',
                optimizer=optimizer,
                metrics=['mae'])
  return model

model = build_model()
model.summary()

# Display training progress by printing a single dot for each completed epoch
class PrintDot(keras.callbacks.Callback):
  def on_epoch_end(self, epoch, logs):
    if epoch % 100 == 0: print('epoch: ',epoch)
    #print('.', end='')

EPOCHS = 200

# Store training stats
history = model.fit(train_x, train_y, epochs=EPOCHS,
                    validation_split=0.2, verbose=0,
                    callbacks=[PrintDot()])

import matplotlib.pyplot as plt


def plot_history(history):
  plt.figure()
  plt.xlabel('Epoch')
  plt.ylabel('Mean Abs Error [1000$]')
  plt.plot(history.epoch, np.array(history.history['mean_absolute_error']),
           label='Train Loss')
  plt.plot(history.epoch, np.array(history.history['val_mean_absolute_error']),
           label = 'Val loss')
  plt.legend()
  plt.ylim([0, 10])
  plt.show()

plot_history(history)

[loss, mae] = model.evaluate(test_x, test_y, verbose=0)

print("Testing set Mean Abs Error: ${:7.2f}".format(mae * 1000))

test_predictions = model.predict(test_x).flatten()

plt.scatter(test_y, test_predictions)
plt.xlabel('True Values [1000$]')
plt.ylabel('Predictions [1000$]')
plt.axis('equal')
plt.xlim(plt.xlim())
plt.ylim(plt.ylim())
_ = plt.plot([-100, 100], [-100, 100])
plt.show()

error = test_predictions - test_y
plt.hist(error, bins = 50)
plt.xlabel("Prediction Error [1000$]")
_ = plt.ylabel("Count")
plt.show()
```
