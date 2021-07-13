# SpringCloud学习总结之框架简介

Spring cloud是基于Spring Boot实现的一套微服务架构工具集，包含服务治理、配置管理、熔断器等，为微服务开发者提供了一套简单易懂、易部署和易维护的分布式系统开发工具包。

## 1.Spring Cloud Netflix

**Eureka：** 注册中心，服务治理组件，提供服务注册和服务发现的能力。

**Ribbon：** 负载均衡的服务调用组件，提供多种负载均衡策略。

**Hystrix：** 服务容错组件，实现熔断器模式，为依赖服务的出错和延迟提供了容错能力。

**Feign：** 基于Ribbon和Hystrix的声明式调用组件。

**Zuul：** API网关组件，提供请求路由和过滤能力。

## 2.Spring Cloud Config

分布式配置中心，实现分布式系统中配置信息的外部存储，提供客户端的配置刷新和加密解密等操作，默认使用Git存储配置。

## 3.Spring Cloud Bus

分布式消息总线，通过轻量级消息代理连接各个分布式节点，用来动态刷新集群中的服务配置。

## 4.Spring Cloud Security

基于spring security的安全工具包，为你的应用程序添加安全控制。

## 5.Spring Cloud Stream

消息组件，基于 Redis，Rabbit，Kafka 实现的消息微服务，简单声明模型用以在 Spring Cloud 应用中收发消息。
