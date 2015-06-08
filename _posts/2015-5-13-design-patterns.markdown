---
published: true
title: 常见设计模式
layout: post
---
设计模式：

1. 单例 只有一个实例  LayoutInflater
2. Builder 不关心产品内部实现 AlertDiaglog
3. 外观模式 只与最外层的类进行交互，具体实现交给一个统一的对象进行 Context
4. 模板模式 封装不变的部分，拓展可变的部分 AsyncTask
5. 适配器模式 把原来不适配的接口进行转达到适配的目的 Adapter
6. 观察者模式 定义一种一对多的依赖关系，当被依赖者发生变化时，所以依赖它的对象都会收到通知，可用来做消息队列、事物总线 ListView notifyDataSetChanged EventBus
7. 策略模式 针对同一类型的问题有多种处理方式，具体行为有差异的时候可以使用，比如大量的if-else或者switch-case的时候，可以用一个统一的接口来让子类实现从而进行不同的处理
8. 代理模式 给一个对象提供代理对象，并由代理对象控制对原对象的引用
9. 原型模式 类的初始化需要耗费非常多的资源，通过原型拷贝可以避免这些消耗 Intent.clone