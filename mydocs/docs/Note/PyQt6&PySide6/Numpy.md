# Numpy

> 一直以来把numpy当做是“用的时候才去学”的工具，恰巧最近在复盘MIT18.06，就顺手记录一下numpy在线性代数中的一些计算方法

直接贴出我在终端中的交互记录：

```bash
wayne@wayne-Legion:~$ python3
Python 3.10.12 (main, Feb  4 2025, 14:57:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import numpy as np
>>> np.array([1, 2, 3, 4, 5, 6])
array([1, 2, 3, 4, 5, 6])
>>> sample = np.array([1, 2, 3, 4, 5, 6])
>>> sample.shape
(6,)
-------------------------------------------
>>> a = np.array([1, 2, 3])
>>> b = np.array([2, 9, 5])
>>> a + b
array([ 3, 11,  8]
--------------------------------------------
>>> a = np.array([1, 2, 3])
>>> b = np.array([2, 9, 5])
>>> a.dot(b)
35
>>> a @ b
35
>>> np.cross(a, b)
array([-17,   1,   5]
--------------------------------------------
>>> a
array([[1, 2],
       [3, 4]])
>>> a.T
array([[1, 3],
       [2, 4]])
>>> np.linalg.inv(a)
array([[-2. ,  1. ],
       [ 1.5, -0.5]])
>>> np.linalg.det(a)
-2.0000000000000004
--------------------------------------------
>>> a
array([[1, 2],
       [3, 4]])
>>> np.linalg.eig(a)
EigResult(eigenvalues=array([-0.37228132,  5.37228132]), eigenvectors=array([[-0.82456484, -0.41597356],
       [ 0.56576746, -0.90937671]]))
>>> eigenvalues, eigenvectors = np.linalg.eig(a)
>>> eigenvalues
array([-0.37228132,  5.37228132])
>>> eigenvectors
array([[-0.82456484, -0.41597356],
       [ 0.56576746, -0.90937671]])
---------------------------------------------
>>> a = np.array([[1, 2, 3], [4, 5, 6]])
>>> a.shape
(2, 3)
>>> b = a.T
>>> b
array([[1, 4],
       [2, 5],
       [3, 6]])
>>> b.shape
(3, 2)
>>> a @ b
array([[14, 32],
       [32, 77]])
>>> b @ a
array([[17, 22, 27],
       [22, 29, 36],
       [27, 36, 45]])
>>> b.dot(a)
array([[17, 22, 27],
       [22, 29, 36],
       [27, 36, 45]])
```

