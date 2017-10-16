---
layout: post
title: Tensorflow beginning
tags:
- Tensorflow
categories: MachineLearning

description: Basic knowledge learning for tensorflow
---
## Tensorflow系咩野
Tensorflow，一个机器学习库

## 小笔记
### 如何导入哩个库？

```python
import tensorflow as tf
```

### 使用场合？

- 研究，开发和迭代新打机器学习架构

- 将模型从训练直接切换到部署

- 实现已有的复杂架构

- 大规模分布式模型

- 为移动/嵌入式系统创建和训练模型

### 测试一下

```python
import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt

a = tf.random_normal([2,20])
sess = tf.Session()
out = sess.run(a)
x, y = out

plt.scatter(x, y)
plt.show()
```





