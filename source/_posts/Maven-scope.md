---
title: Maven 构建 scope 详解
date: 2019-10-30 09:39:20
tags:
   - Maven
categories:
   - Maven
toc: true
declare: true
---

使用Maven构建项目已经很久了，但是经常使用的默认配置向；默认的依赖配置项中，scope的默认值是compile；还有很多其他值都不太清楚具体作用，今天详细学习下 scope 不同值的作用；

<!-- more -->

## Maven 构建中 scope 详解

- Maven 的哲学思想是，约定优于配置（Convention Over Configuration），Maven 依赖中 scope 的默认值是compile
- Scope 指定了依赖（第三方jar包）的 作用范围
- 作用范围包括，所在项目的测试、编译、运行、打包等生命周期
- 其中，编译和运行还分为
  - 测试代码的编译和运行
  - 非测试代码的编译和运行

### scope 的分类

#### test 测试范围

测试范围的依赖（第三方jar包），针对测试相关代码的编译和运行，在通常代码的编译和运行时都不需要，只有在有关测试的代码编译和运行测试代码阶段可用

#### compile 编译范围

依赖默认范围，该依赖需要参与当前项目的编译、测试、运行、打包

#### runntime

- 表示依赖无需参与当前项目的编译，但是后期的运行和测试需要参与
- 与 compile 相比，跳过编译而已
- 比如，你可能在编译的时候需要 JDBC API JAR，只有在 运行时才需要 JDBC
- 貌似是编译时该包不参与，运行时参与

#### provided

>打包的时候可以不用包进去，别的设施会提供。事实上该依赖理论上可以参与编译，测试，运行等周期。相当于compile，但是打包阶段做了exclude操作

- 应用场景是你定义了一个Servlet，此刻得需要Servlet-api.jar 才能编译成功，但是当你达成war 包时，你并不想将 Servlet-api.jar 包进去，因为Tomcat等容器会提供
- 跟compile 类似，说明JDK、容器或使用者会提供这个依赖，如Servlet.jar
- 这个依赖只作用在** 编译和测试，该依赖会由系统组件提供，不需手动添加，只存在编译、运行、测试阶段，打包是不用包进去，打包阶段做了exclude 动作
- 没有传递性

#### system

被依赖项不会从maven仓库下载，而是从本地系统指定路径下寻找，需要 systemPath 属性

-----

### scope 的依赖传递

> A -> B -> C, 当前项目 A，A 依赖于 B，B 依赖于 C，知道 B 在 A 中的 scope，怎么知道 C 在 A 中的 scope

- A 需不需要 C 的问题，本质由 C 在 B 中的 scope 决定
- 当 C 在 B 中的 scope 是 test 或 provided 时，C **直接被丢弃，A 不依赖 C**
- 否则 A 依赖 C，C 的 scope 继承与 B 的 scope

-----

### 参考

[Maven 依赖中 scope 详解](https://www.jianshu.com/p/a9bd44a83dc5)