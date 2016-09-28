---
layout: post
title: 【读书笔记】自定义控件
tags: [Android,读书笔记,Android群英传]
comments: true
categories: jekyll
---
###  Android 控件架构
``` markdown
* 在Android中，控件分为两类(ViewGroup,View)。


* **ViewGroup**可以作为父控件包含多个**View**,并管理其包含的**View**。
 	##### 控件树--通过 **ViewGroup** 使整个界面上的控件形成一个树状结构,上层控件负责下层子控件的测量与绘制,并传递交互事件) 


* ***findViewById()*** 方法,就是在控件树中以数的深度优先遍历来查找对应元素。在每棵控件树的顶部,都有一个**ViewParent**对象来统一调度和分配所有的交互管理事件。


* **View**所有的监听事件，都通过***WindowManagerService***来进行接收，并通过**Activity**对象来回调相应的***onClickListener***
* 
* **Activity**的***requestWindowFeature()*** 实际上执行的是**PhoneWIndow**的***requestFeature()*** 方法，而**PhoneWIndow**的优先级要比**ContentView**(也就是**Activity**对象)要高，所以**Activity**的***requestWindowFeature()*** 方法要在***setContentView()*** 方法之前执行。
``` 
[具体可以在这查看](http://blog.csdn.net/kuai_jia_long/article/details/45834343)

