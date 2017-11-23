---
layout: post
title: Spring Boot beginning
tags:
- Sprintboot
categories: Web

description: Basic knowledge learning for Sprint Boot
---
## HelloWolrd踩坑日记
### 第一个坑
高人指点：[参考链接1][1]
spring boot正常启动之后无法访问报404的解决办法
正常启动了，但是我写了一个controller ，用的@RestController 注解去配置的controller，然后路径也搭好了，但是浏览器一直报404. 最后原因是，spring boot只会扫描启动类当前包和以下的包
比如：主程序是BoothelloworldApplication，controller就要放在主程序包com.lyon.boothelloworld下（可以再建包）
![sprintboot1.jpg](https://www.z4a.net/images/2017/11/23/sprintboot1.jpg)


  [1]: https://www.cnblogs.com/daixinyu/p/6843335.html