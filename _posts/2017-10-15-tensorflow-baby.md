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

### 第一个坑

```python
import tensorflow as tf

a = tf.constant(5, name="input_a")
b = tf.constant(3, name="input_b")
c = tf.multiply(a, b, name="mul_c")
d = tf.add(a, b, name="add_d")
e = tf.add(c, d, name="add_e")

sess = tf.Session()
sess.run(e)

writer = tf.summary.FileWriter("my_graph", sess.graph)
```

然后在命令行运行

```
tensorboard --logdir="my_graph"
```

命令行就会提示

```
TensorBoard 0.1.5 at http://localhost:6006 (Press CTRL+C to quit) 
```

这时如果在浏览器输入**http://localhost:6006**，然后切换到graph，会提示下面找不到graph到错误

![2017-11-01-23-30-04.png](https://www.z4a.net/images/2017/11/01/2017-11-01-23-30-04.png)

查了半天，换了如下方式，一样错误

- FileWriter("my_graph", sess.graph) 里面到my_graph路径换成绝对路径

- 上面的路径换成用单引号包裹

- tensorboard --logdir="my_graph" 这里面到my_graph换成绝对路径

- 上面的路径换成单引号包裹

- 路径里面避免中文字符、升级tensorflow和tensorboard、换chrome浏览器之类

最后思考，为什么要有建立一个my_graph文件夹，有一个空的文件夹就可以输出图片？里面要不要有什么东西？原来里面需要有一个event文件，就是用来显示graph的，补充下面代码，输出event文件到指定文件夹

```python
writer.close()
sess.close()
```

然后运行整段代码，event文件就在my_graph生成了，大概如下格式

```
events.out.tfevents.111111111.aaaa
```

现在再运行

```
tensorboard --logdir="my_graph"
```

打开相应地址，选择graphs，图片就出现了！

![2017-11-01-23-48-25.png](https://www.z4a.net/images/2017/11/01/2017-11-01-23-48-25.png)

