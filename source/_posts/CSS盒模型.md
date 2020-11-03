---
layout: 'n'
title: CSS盒模型
date: 2020-06-21 18:34:45
tags: 学习
top: 15
---
# CSS盒模型
<!--more-->
## 1.盒子模型

    （1）标准盒子模型：content不包括padding和border

    （2）IE盒子模型：content包括padding和border 

## 2.js如何设置获取盒模型对应的宽和高

    （1）dom.style.width/height

    （2）dom.currentStyle.width/height（只有IE支持）

    （3）window.getComputedStyle(dom).width/height （大部分浏览器支持）

    （4）dom.getBoundingClientRect().width/height （绝对）

## 3.BFC原理 （边距重叠解决方案）
     BFC:块级格式化上下文
     原理：BFC是一个独立的容器；BFC这个元素的垂直方向的元素会发生重叠；BFC的区域不会与浮动元素的box重叠；计算BFC高度时浮动元素也会参加计算。
     创建BFC：
    （1）根元素
    （2）float属性不为none
    （3）position不为static和relative
    （4）overflow不为visible
    （5）display为inline-block, table-cell, table-caption, flex, inline-flex