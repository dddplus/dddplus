<img src="doc/assets/img/logo-small.png">

#### **[Quickstart](#quickstart)** • **[Examples](#the-demo)** • **[Landscape](#landscape-of-central-platform)** • **[Chat with us](https://gitter.im/cp-ddd-framework/community)**

[![Mavenn Central](https://img.shields.io/maven-central/v/io.github.dddplus/dddplus.svg?label=Maven%20Central)](https://search.maven.org/search?q=g:io.github.dddplus)
![Requirement](https://img.shields.io/badge/JDK-8+-blue.svg)
[![CI](https://github.com/funkygao/cp-ddd-framework/workflows/CI/badge.svg?branch=master)](https://github.com/funkygao/cp-ddd-framework/actions?query=branch%3Amaster+workflow%3ACI)
[![Code Quality: Java](https://img.shields.io/lgtm/grade/java/g/funkygao/cp-ddd-framework.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/funkygao/cp-ddd-framework/context:java)
[![Maintainability](https://api.codeclimate.com/v1/badges/84b05607593179e62374/maintainability)](https://codeclimate.com/github/funkygao/cp-ddd-framework/maintainability)
[![Coverage Status](https://img.shields.io/codecov/c/github/funkygao/cp-ddd-framework.svg)](https://codecov.io/gh/funkygao/cp-ddd-framework)

[![Mentioned in Awesome DDD](https://awesome.re/mentioned-badge.svg)](https://github.com/heynickc/awesome-ddd#jvm)
[![Javadoc](https://img.shields.io/badge/javadoc-Reference-blue.svg)](https://funkygao.github.io/cp-ddd-framework/doc/apidocs/)
[![TODO](https://badgen.net/https/api.tickgit.com/badgen/github.com/funkygao/cp-ddd-framework?label=todos)](https://www.tickgit.com/browse?repo=github.com/funkygao/cp-ddd-framework)
[![Gitter chat](https://img.shields.io/badge/gitter-join%20chat%20%E2%86%92-brightgreen.svg)](https://gitter.im/cp-ddd-framework/community)

<details>
<summary><b>Table of content</b></summary>

## Table of content
* [What is DDDplus](#what-is-dddplus)
    * [Current status](#current-status)
    * [Quickstart](#quickstart)
    * [Features](#features)
    * [Modules](#modules)
    * [Key abstractions](#key-abstractions)
* [Using DDDplus](#using-dddplus)
    * [Maven](#maven)
    * [Gradle](#gradle)
    * [Building from Source](#building-from-source)
    * [With dddplus-archetype](#with-dddplus-archetype)
* [Demos](#demos)
* [DDDplus Ecosystem](#dddplus-ecosystem)
* [FAQ](#faq)
* [Landscape of Central Platform](#landscape-of-central-platform)
* [Contribution](#contribution)
* [Release Planning](#release-planning)
* [Licensing](#licensing)

</details>

----

## What is DDDplus?

DDDplus, originally cp-ddd-framework(cp means Central Platform：中台), is a lightweight flexible development framework for complex business architecture.

Originated from business，serve business！

一套轻量级业务中台开发框架，以[DDD](https://github.com/funkygao/cp-ddd-framework/wiki/DDD)思想为本，致力于业务资产的可沉淀可传承，全方位解决复杂业务场景的扩展问题，实现[中台核心要素](https://github.com/funkygao/cp-ddd-framework/wiki/%E4%B8%9A%E5%8A%A1%E4%B8%AD%E5%8F%B0%E7%9A%84%E6%A0%B8%E5%BF%83%E8%A6%81%E7%B4%A0)，赋能中台建设。

融合了前中台复杂生态协作方法论，充分考虑组织架构、技术债、学习门槛、可演进性、运维成本和风险而开发的，解决[业务开发痛点](https://github.com/funkygao/cp-ddd-framework/wiki/Why-we-need-this-framework)，是中台架构的顶层设计和完整解决方案。

从业务中来，到业务中去！

### Current status

Used for several complex critical central platform projects in production environment.

多个复杂的中台核心项目生产环境下使用。

### Quickstart

Please visit [Quickstart](https://github.com/funkygao/cp-ddd-framework/wiki).

### Features

- Based on DDD, but beyond DDD
- 14 key business abstractions cover most complex business scenarios
- Full layered extensibility
- Empowers InnerSource
- Provide maven archetype that generates a DDDplus integrated project
- Total solutions oriented
- Above all, DDDplus is simple enough

核心特性：
- 以DDD架构思想为本，面向复杂业务场景架构设计
    - 通过代码框架提供足够的约束和指导，让DDD不再仅停留在思想层面
    - 只引入弱依赖的 [IDomainModel](dddplus-spec/src/main/java/io/github/dddplus/model/IDomainModel.java)，弱化其他概念，降低DDD上手门槛
    - 提供 [dddplus-archetype](https://github.com/dddplus/dddplus-archetype)，直接生成最佳实践的脚手架代码
    - DDD分层架构上增加一层`spec layer`，解决前中台协同问题
- 14个核心业务抽象(常用9个)，勾勒出业务中台骨架
    - 中台架构的顶层设计
    - less is more，以不变应万变
    - 研发专注于填空式开发，只需解决局部问题
- 全方位解决业务的不确定性
    - 业务逻辑、流程、逻辑模型、数据模型的扩展、多态体系
    - 框架本身支持再次扩展，便于被集成
    - 抽象出独立的业务扩展包，框架底层通过`ClassLoader`机制进行业务隔离，支持热更新
    - 平台容器包、平台业务包与业务扩展包：分离
- 支撑中台战略的复杂生态协作
    - 前台、中台解耦
    - 业务隔离，不同前台间业务隔离，前台和中台隔离
    - 支持稳态、敏态双速应用
    - InnerSource，生态合作协同机制
- 完整的解决方案
    - 业务能力演化，业务测试，最佳实践，架构持续防腐，重构的导流验证，绞杀者落地方案等
    - 提供 [一套完整的Demo工程](https://github.com/dddplus/dddplus-demo)
    - 演示 [5分钟搭建一个仓储中台WMS](https://github.com/dddplus/dddplus-archetype-demo)，手把手真实场景教学
- DDDplus框架，始终保持简单性

### Modules

```
dddplus
   ├── dddplus-spec    - Specification of DDDplus
   ├── dddplus-runtime - Runtime implementation
   ├── dddplus-plugin  - Plugin jar hot reloading mechanism
   ├── dddplus-unit    - Extra unit test facilities
   ├── dddplus-enforce - Enforce expected evolvement of the business architecture
   └── dddplus-test    - Fully covered unit test cases
```

### Key abstractions

![](http://www.plantuml.com/plantuml/svg/VLJ1JXj13BtxAonwIKGJH7khLX4geH8z8CGFL6RNoOxOp4GURrC4-VTwo6IpoG8vnNvlxFSydhsAIgBjge7uvFoQX5POawysubJPuuAQo3qirbI5ZVFBejWuhV_iujaCLLg6XXUA6b3SibQid72fBdY0DPLFj6HSD-tIUIoANrQCxTWBeFsSLvO5bOotjnLxTVhym34qVrbEyNbOaVCt_vHzjDAdyBqreCU61_dGkFBvBKlU1wMa2-z9rBCCqweiVf1-jyP1oXR0iendTL0KRW9LISePKiIxIyZUfzCKGASKYzV9PE1hW0_c0XqNVs0PAXvbsHVPrSLExnYWf_OXjCQnr6DKeLBn9qNEoSDVg_Xb4UI6ohhhCXgV4fn4_H1-sNVOudd52sgR8-vyFa-ac6ILHcdtHz_7TbOC6yp1c2lIiXvro1Y6hDqGyu0-XFCsGDuMAttEUytNQS9MEXkSJlkJo_nKfLkr_ZWAoviho5WNmtNmIiwp71bEcvEkt_dV9ADqjr_HL8xx_CbabbyJG1QUzm2opM6u5XV4R1-znpXuZTqzNLgNrzaXFaQ_VOf-_nIzEqMt05Vig_GX-Wy0)

## Using DDDplus

已推送至[Maven中央库](https://search.maven.org/search?q=g:io.github.dddplus)，可直接引入。

### Maven

```xml
<dependency>
    <groupId>io.github.dddplus</groupId>
    <artifactId>dddplus-runtime</artifactId>
    <version>1.1.2</version>
</dependency>
```

### Gradle

```groovy
dependencies {
    ...
    compile 'io.github.dddplus:dddplus-runtime:1.1.2'
}
```

### Building from Source

``` bash
git clone https://github.com/funkygao/cp-ddd-framework.git
cd cp-ddd-framework/
mvn install
```

### With dddplus-archetype

``` bash
mvn archetype:generate                          \
    -DarchetypeGroupId=io.github.dddplus        \
    -DarchetypeArtifactId=dddplus-archetype     \
    -DarchetypeVersion=1.1.1                    \
    -DgroupId=com.foo -DartifactId=demo         \
    -Dpackage=com.foo -Dversion=1.0.0-SNAPSHOT  \
    -B
```

For more, please visit [dddplus-archetype project](https://github.com/dddplus/dddplus-archetype).

## Demos

- [使用DDDplus搭建`订单履约中台`的例子](https://github.com/dddplus/dddplus-demo)
- [使用DDDplus，5分钟搭建一个仓储中台WMS](https://github.com/dddplus/dddplus-archetype-demo)

## DDDplus Ecosystem

- [dddplus-archetype](https://github.com/dddplus/dddplus-archetype)
    - a maven archetype that generates a complete DDDplus driven project skeleton
- [dddplus-visualizer](https://github.com/dddplus/vis)
    - a CLI parsing DDDplus driven project Java AST with ANTLR and visualize your business artifacts


## DDD建模构造块

>There's a construct for everything.
>Every developer has a different name for these constructs.

提供细粒度的精确模型构造块，研发根据问题对号入座，才可能实现出好的业务模型。

- 确定性问题
    - IBag，封装集合逻辑
    - (IUnboundedDomainModel, BoundedDomainModel)，上下文角色对象
    - (DirtyMemento, IDirtyHint), IMergeAwareDirtyHint)，追踪领域对象状态变化，通过乐观锁实现落库
    - Exchange，domain与infrastructure间传递非领域数据的容器
    - ISpecification，业务校验和场景识别
    - INativeFlow，可复用的流程片段
    - AbstractBusinessNo，业务编号建模
    - IGateway，远程RPC的防腐层
    - IUnitOfWork，跨聚合根的事务
- 不确定问题
    - IDomainExtension，扩展点
    - (Policy, Router)，扩展点的两种路由方式
    - Pattern，全局业务模式
    - IIdentity，业务身份
- 技术组件
    - [mapstruct](https://mapstruct.org/)，对象转换
- 长效机制
    - DDDPlusEnforcer，业务建模规范的架构守护

## FAQ

Please visit [FAQ](https://github.com/funkygao/cp-ddd-framework/wiki/FAQ).

## Landscape of Central Platform

业务中台建设全景图。

![](doc/assets/img/landscape.png)

## Contribution

You are welcome to contribute to the project with pull requests on GitHub.

If you find a bug or want to request a feature, please use the [Issue Tracker](https://github.com/funkygao/cp-ddd-framework/issues).

For any question, you can use [Gitter Chat](https://gitter.im/cp-ddd-framework/community) to ask.

## Release Planning

Interested on when the next release is coming? Check our [release planning](https://github.com/funkygao/cp-ddd-framework/wiki/Release-Planning) document for details.

## Licensing

DDDplus is licensed under the Apache License, Version 2.0 (the "License"); you may not use this project except in compliance with the License. You may obtain a copy of the License at [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0).
