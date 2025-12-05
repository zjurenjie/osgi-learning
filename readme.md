# OSGI框架相关学习

## 什么是OSGI（Open Service Gateway Initiative）？

随着k8s、容器等技术广泛流行以及SpringBoot提供的`fat jar`模式，java程序发布往往将所有class和resource打成一个“胖包”构建成docker镜像，直接部署在ks集群中。但是对于非容器集群运行环境，如工业互联网上本地单机服务器、KVM虚拟机场景，使用微服务模式开发，多个微服务部署在同一个服务器。受限于服务器存储资源，微服务共同依赖一个本地maven仓库，微服务一般采用”瘦包“的方式发布，只发布业务组件包。此时就会面临**动态依赖拉取**、**类加载**、**远端发布本地部署**的一系列问题，OSGI组件就是解决此类问题场景

OSGi（Open Service Gateway Initiative）是**Java 平台的模块化（组件化）规范与运行时框架**，核心目标是解决传统 Java 应用的 “模块化缺陷”（如 JAR 地狱、静态部署、类冲突、模块紧耦合等问题），为 Java 应用提供**精细化的模块化管理、动态部署能力和松耦合的服务交互模型**。

简单来说，OSGi 就像给 Java 应用搭建了一个 “模块化操作系统”，让复杂应用能被拆分为独立的 “模块（Bundle）”，并实现模块的动态管理和灵活协作。

## 常用的开源OSGI组件

OSGI 框架是所有 OSGI 组件运行的基础，主流实现有 3 个：

1. [Eclipse Equinox](https://github.com/eclipse-equinox/equinox)
   - **特点**：Eclipse IDE 的核心底层框架，实现了 OSGI Core Specification（最新支持 OSGi R9），功能全面、稳定性高，是 Java 桌面应用和企业级应用中最常用的 OSGI 框架之一。
   - **典型场景**：Eclipse 插件开发、基于 OSGI 的桌面应用、企业级模块化系统。

2. [Apache Felix](https://github.com/apache/felix)
   - **特点**：Apache 基金会的轻量级 OSGI 框架，模块化程度更高、体积更小，对嵌入式系统和轻量级服务端更友好，是 OSGI 生态中最活跃的实现之一。
   - **典型场景**：嵌入式设备、微服务网关、轻量级企业应用。

3. [Apache Karaf](https://github.com/apache/karaf)
   - **特点**：基于 Apache Felix（默认）或 Eclipse Equinox 的 OSGI 容器，集成了大量企业级组件（如 HTTP 服务、配置管理、日志、安全），支持热部署、模块化配置和命令行管理（Gogo Shell），是目前最流行的 OSGI 服务端容器。
   - **扩展**：Apache Karaf 还衍生出 Karaf Cellar（分布式 OSGI 集群）、Karaf Decanter（监控）等组件。


三个框架的活跃数如下，其中

![star-history-2025125](https://github.com/zjurenjie/osgi-learning/blob/master/document/star-history-2025125.png)

## OSGI入门实践

### [Apache Felix入门实践](https://github.com/zjurenjie/osgi-learning/blob/master/document/apache-felix/readme.md)

Apache Felix入门实践