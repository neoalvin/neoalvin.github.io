# SpringCloud学习总结之配置文件

SpringCloud的配置目录在项目中的src/main/resources，其中application.properties是SpringCloud的默认配置文件，可以在配置文件中定义端口号、服务器地址、数据源等信息，也可以定义自定义属性。

## 1.配置文件格式

SpringCloud中默认使用.properties格式的配置文件，同时也支持.yml（YAML）格式，具体格式信息参考如下。

```yaml
# YAML格式配置文件
server:
  # 配置服务端口
  port: 8081
eureka:
  client:
    service-url:
      # 配置eureka服务器地址
      defaultZone: http://localhost:8081/eureka
```

```properties
# Properties格式配置文件
# 配置服务端口
server.port: 8081
# 配置eureka服务器地址
eureka.client.service-url.defaultZone: http://localhost:8081/eureka
```

## 2.**配置参数引用**

Spring Cloud可以在配置文件和代码中通过${key}的方式调用已配置的属性值，而且可以调用${random}来生成随机的字符串、int、long等类型的数据。

（1）配置文件中可以引用前面已定义的属性值

```properties
#服务ID
service.id=${random.int(16)}
#服务名
service.name=service-demo 
#服务地址
service.url=https://${service.name}.com 
```

（2）代码中可以通过@Value注解引用配置文件中定义的属性值

```java
public class ServiceInfo {
    @Value("${service.name}")
    private String serviceName;

    @Value("${service.url}")
    private String serviceUrl;
}
```



## 3.多环境配置

开发过程中，为了满足开发、测试、生产环境的隔离，我们可以根据使用场景准备多套配置文件，以application-{profile}.properties的形式放在跟application.properties同级目录下，并在application.properties中通过指定spring.profiles.active={profile}来激活当前环境的配置。例如如下三种环境的配置文件：

- application-dev.properties
- application-test.properties
- application-prod.properties

如果我们当前是开发环境，则只需要在application.properties文件中设置下面值：

```properties
spring.profiles.active=dev
```



## 4.加载顺序

bootstrap.yml：位于jar包外的优先级最高

application.yml： 配置中心的文件 > JVM参数配置> 本地active指定文件 > 本地default文件

优先级高的会覆盖优先级低的重复的配置项值
