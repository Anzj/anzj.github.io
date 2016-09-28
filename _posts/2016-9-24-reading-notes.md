---
layout: post
title: 【读书笔记】自定义控件
tags: [Android,读书笔记,Android群英传]
comments: true
categories: jekyll
---
###  Android 控件架构

```
1.在Android中，控件分为两类(ViewGroup,View)。
2.ViewGroup可以作为父控件包含多个View,并管理其包含的View。
  1) 控件树--通过ViewGroup使整个界面上的控件形成一个树状结构,上层控件负责下层子控件的测量与绘制,
  并传递交互事件) 
3.findViewById()方法,就是在控件树中以数的深度优先遍历来查找对应元素。
4.在每棵控件树的顶部,都有一个ViewParent对象来统一调度和分配所有的交互管理事件。
5.View所有的监听事件，都通过WindowManagerService来进行接收，并通过Activity对象来回调相应的 
onClickListener。

```
