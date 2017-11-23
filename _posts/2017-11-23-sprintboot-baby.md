---
layout: post
title: Spring Boot beginning
tags:
- Sprintboot
categories: Web

description: Basic knowledge learning for Sprint Boot
---
## 踩坑日记
### 第一个坑
高人指点：[参考链接][1]
```
spring boot正常启动之后无法访问报404的解决办法
正常启动了，但是我写了一个controller ，用的@RestController 注解去配置的controller，然后路径也搭好了（这里也不是我的代码问题，用了spring mvc这么多年），但是浏览器一直报404.最后原因是，spring boot只会扫描启动类当前包和以下的包  。 如果将 spring boot 放在 包  com.dai.controller 里面的话 ，它会扫描 com.dai.controller 和 com.dai.controller.* 里面的所有的  
```


  [1]: https://www.cnblogs.com/daixinyu/p/6843335.html