# 数据预处理

## 第 1 步：导入库

```py
import numpy as np
import pandas as pd
```

## 第 2 步：导入数据集

```py
dataset = pd.read_csv('Data.csv') // 读取csv文件
X = dataset.iloc[ : , :-1].values // .iloc[行，列]
Y = dataset.iloc[ : , 3].values   // : 全部行 or 列；[a]第a行 or 列
                                  // [a,b,c]第 a,b,c 行 or 列
```

## 第 3 步：处理丢失数据

```py
from sklearn.preprocessing import Imputer
imputer = Imputer(missing_values = "NaN", strategy = "mean", axis = 0)
imputer = imputer.fit(X[ : , 1:3])
X[ : , 1:3] = imputer.transform(X[ : , 1:3])
```

## 第 4 步：解析分类数据

```py
from sklearn.preprocessing import LabelEncoder, OneHotEncoder
labelencoder_X = LabelEncoder()
X[ : , 0] = labelencoder_X.fit_transform(X[ : , 0])
```

### 创建虚拟变量

```py
onehotencoder = OneHotEncoder(categorical_features = [0])
X = onehotencoder.fit_transform(X).toarray()
labelencoder_Y = LabelEncoder()
Y =  labelencoder_Y.fit_transform(Y)
```

## 第 5 步：拆分数据集为训练集合和测试集合

```py
from sklearn.cross_validation import train_test_split
X_train, X_test, Y_train, Y_test = train_test_split( X , Y , test_size = 0.2, random_state = 0)
```

## 第 6 步：特征量化

```py
from sklearn.preprocessing import StandardScaler
sc_X = StandardScaler()
X_train = sc_X.fit_transform(X_train)
X_test = sc_X.transform(X_test)
```
