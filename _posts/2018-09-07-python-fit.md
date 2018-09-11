---
layout: default
title:  "Data Fit"
date:   2018-09-07 21:30:00 +0800
categories: python
---

## plot data

```python
import matplotlib.pyplot as plt
import numpy as np

x, y = np.loadtxt('ss.txt', delimiter='\t', unpack=True)
plt.plot(x,y, label='test')
plt.xlabel('strain')
plt.ylabel('stress')
plt.title('S-S curve')
plt.legend()
plt.show()
```

***

## fit non-linear function

### LMFIT

```python
# Import the necessary packages and modules
import matplotlib.pyplot as plt
import numpy as np
from lmfit import Model

x, y = np.loadtxt('ss.txt', delimiter='\t', unpack=True)

def expfunc(x, scale):
    # "model exponential decay with offset"
    return scale*(x - 1/x)

# create model from the above model function
model = Model(expfunc)

# create parameters with initial values, 
# using names from model function
params = model.make_params(scale=1)

# fit data 'y' to model with params
result = model.fit(y, params, x=x)

# print and plot result 
print(result.fit_report())
result.plot_fit()
plt.show()
```

***

### Ref.

- [Loading Data from Files for Matplotlib](https://pythonprogramming.net/loading-file-data-matplotlib-tutorial/)
- [LMFIT](https://lmfit.github.io/lmfit-py/index.html)
- [stackoverflow](https://stackoverflow.com/questions/47875092/non-linear-regression-for-finding-parameters-in-python)