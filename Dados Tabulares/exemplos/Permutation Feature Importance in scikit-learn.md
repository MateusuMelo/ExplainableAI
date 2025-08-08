


```python
import sklearn

import pandas as pd
import numpy as np
import tensorflow as tf
import matplotlib.pyplot as plt

from sklearn.datasets import fetch_california_housing
from sklearn.model_selection import train_test_split
```

## Load dataset

```python
X = cal_housing.data 
y = cal_housing.target 
cal_features = cal_housing.feature_names 
df = pd.concat((pd.DataFrame(X, columns=cal_features), pd.DataFrame({'MedianHouseVal': y})), axis=1)
```
