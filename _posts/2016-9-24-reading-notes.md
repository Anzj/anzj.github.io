---
layout: post
title: 【读书笔记】自定义控件
tags: [Android,读书笔记,Android群英传]
comments: true
categories: jekyll
---
##  Android 控件架构

 1. 在 **Android** 中，控件分为两类( **ViewGroup** , **View** )。


 2. **ViewGroup**可以作为父控件包含多个**View**,并管理其包含的**View**。
 	
     * 控件树--通过 **ViewGroup** 使整个界面上的控件形成一个树状结构,上层控件负责下层子控件的测量与绘制,并传递交互事件) 


 3. ***findViewById()*** 方法,就是在控件树中以数的深度优先遍历来查找对应元素。在每棵控件树的顶部,都有一个**ViewParent**对象来统一调度和分配所有的交互管理事件。


 4. **View**所有的监听事件，都通过***WindowManagerService***来进行接收，并通过**Activity**对象来回调相应的***onClickListener***

 5. **Activity**的***requestWindowFeature()*** 实际上执行的是**PhoneWIndow**的***requestFeature()*** 方法，而**PhoneWIndow**的优先级要比**ContentView**(也就是**Activity**对象)要高，所以**Activity**的***requestWindowFeature()*** 方法要在***setContentView()*** 方法之前执行。[具体可以在这查看](http://blog.csdn.net/kuai_jia_long/article/details/45834343)
 *当程序在 ***onCreate()*** 方法中调用  ***setContentView()*** 方法后, ***ActivityManagerService*** 会回调 ***onResume()*** 方法，此时系统才会把整个 ***DecorView*** 添加到 ***PhoneWindow*** 中，并让其显示出来，从而最终完成界面的绘制。*  所以如果 ***requestWindowFeature()***  在***setContentView()***  方法执行后执行的话，那时界面已经绘制完成并展现出来了，已经不能再执行***PhoneWindow*** 的方法了。
 6. 用于测量View的类——MeasureSpec类，MeasureSpec是一个32位的int值，高2位为测量的模式，低30位为测量的大小。在计算中使用位运算的原因是为了提高并优化效率。
 	

 7. List item

 

