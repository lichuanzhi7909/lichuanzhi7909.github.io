---
published: true
title: 依赖注入
layout: post
---
###什么叫依赖注入
如果在ClassA中有ClassB的实例，则称ClassA对ClassB有一个依赖，直接依赖会有很多问题，比如修改ClassB的生成方式则需要修改ClassA的代码，这个时候我们引入依赖注入的概念，在ClassA中写一个方法，传入ClassB，这样的方式叫做依赖注入

#####依赖注入的好处
* 依赖的注入和配置独立于组件之外（ClassB的注入和生成独立于ClassA）

#####[注解](http://www.trinea.cn/android/java-annotation-android-open-source-analysis/)
* Annotation 分类:
 	1. 标准 Annotation
 	2. 元 Annotation
 	3. 自定义 Annotation
* @Retention 注解保留时间：
	1. SOURCE（源码时），主要用来校验如Override
	2. CLASS（编译时），先自定义类继承AbstractProcessor，再重写process函数
	3. RUNTIME（运行时）
* @Target 可以用来修饰哪些程序元素，如 TYPE, METHOD, CONSTRUCTOR, FIELD, PARAMETER 等，未标注则表示可修饰所有

###常见的依赖注入库
#####[AndroidAnnotation](http://androidannotations.org/)
* 非常强大的依赖注入库，从UI到数据到网络请求都可以实现注入，极大的简化了开发过程，使用apt插件在编译时生成辅助类达到注入效果

缺点：

* 真正的实现在编译生成的子类中，因此在未编译时会有大规模报错，并且编译出错较难定位错位
* 在AndroidStudio测试版的时候apt配置方式经常更新，踩了好多次坑

[使用方法](http://androidannotations.org/)

#####[ButterKnife](http://jakewharton.github.io/butterknife/)
* Jakewharton大神的专注于View的依赖注入库，同样使用编译时的注解方式，生成辅助类来帮助实现注入，可用在Activity、Fragment、Adapter等任意类中
* 7.0.1版本新增了批量进行View操作的功能

[使用方法](http://jakewharton.github.io/butterknife/)

######Dagger
* 使用@Injec来修饰一个类或字段，来表明需要注入，这样Dagger会生成这样一个类的实例来满足需求
* @Module来修饰一个类，表明这个类里面专门提供依赖
* 在Module里使用@Provide告诉Dagger我们需要构造这个对象并提供依赖
* @Component，连接@Inject和@Module，我们需要使用@Component注解一个接口然后列出所有的@Modules组成该组件

