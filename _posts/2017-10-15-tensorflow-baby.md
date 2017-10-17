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

### 第一个例子

```python
import pylab
import tensorflow as tf
import matplotlib.pyplot as plt

a = tf.random_normal([2,20])
sess = tf.Session()
out = sess.run(a)
x, y = out

plt.scatter(x, y)
plt.show()
```

[![Figure_1-1.png](http://www.z4a.net/images/2017/10/18/Figure_1-1.png)](http://www.z4a.net/image/ZxrYb)

*必须加入下面这句，虽然没引用到，但如果不加会报错*

```python
import pylab
```

*如果不加就报这个错*

`RuntimeError: Could not create write struct`

如果使用jupyter notebook，直接运行不了，报上述错误

如果直接整段跑py代码，可以显示图片，但如果想保存为png，一样报错