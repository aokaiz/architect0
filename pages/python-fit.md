---
layout: default
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

## fit non


### Ref.

- [Loading Data from Files for Matplotlib](https://pythonprogramming.net/loading-file-data-matplotlib-tutorial/)
