# 第三章 动态加载与反射构造

> 主要内容
> * 运行时动态加载类
> * 通过反射实例化对象
> * 通过反射增强委托

第二章讲解了如何将反射应用于 **编译时** 可知的类和对象，为了响应快速变化的需求，有时需要向 **运行** 中的应用 **加载新代码**。

Web 服务器就是其中一个例子，比如 Tomcat 支持使用 Servlet 框架进行扩展。Tomcat 是 Java Servlet 框架的参考实现，Servlets 可以视为对 **Tomcat 的扩展**，可以在 Servlet 中定义如何相应请求，这实际上是为 Tomcat 添加了新的行为。

Tomcat 正常工作依赖于能够在运行时 **加载、运行** 新代码，这是通过反射实现的，Java 反射可以在运行时 **动态加载类**，也可以在运行时创建这些类的实例对象。

在 Java 以外，类似功能可部分由动态链接库（DLL）实现，但 DLL 一般 **依赖操作系统**，这会影响跨平台，而且就 **粒度** 而言，DLL 是库，而非类。

本章主要介绍反射的动态加载和动态实例化的特性，借助这些特性，可以实现反序列化。
