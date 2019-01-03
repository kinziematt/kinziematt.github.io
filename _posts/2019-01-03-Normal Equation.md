---
title: "The Normal Equation"
date: 2019-01-03
tags: [machine-learning]
excerpt: "Machine Learning, Linear Regression, Normal Equation"
---

# **Linear Regression (the normal equation)**

*Matthew Dunne*


Use Linear equation normal equation to predict water temperature T_degC  
1) Only use 'Salnty', 'STheta' for predictors  
2) Remove NaN / NA values from dataset (prior to building train/test sets).  
3) Solve for rmse, variance explained, and r-squared.

```python
	import numpy as np
	import os
	import pandas as pd
	from sklearn.model_selection import train_test_split
```

```python
	data=pd.read_csv('C:/Users/mjdun/Desktop/Master Classes/Q3/Machine Learning/Assignments/bottle.csv')
	#use only 'Salnty', 'STheta' for predictors and T_degC as predictor
	data=data[['T_degC','Salnty', 'STheta']]
	#remove NaN/NA values
	data=data.dropna()
	X=data[['Salnty', 'STheta']]
	Y=data['T_degC']
	#split into training and test
	X_train, X_test, y_train, y_test = train_test_split(X, Y, random_state=0)
	X_train.head()
```