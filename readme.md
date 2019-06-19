Spring Cloud 练习

第一次作业<https://github.com/mrgh97/sport-club-1>

第二次作业<https://github.com/mrgh97/sport-club-2>

 第三次作业 <https://github.com/lixingyuan1998/sportclub_3>

第四次作业<https://github.com/lixingyuan1998/sportclub_4>

springcloud 练习 <https://github.com/lixingyuan1998/springcloud_test>


![1560428822867](account-service/src/img/1560428822867.png)





zipkin port:9411

```java
@EnableZipkinServer
```

![1560760625151](account-service/src/img/1560760625151.png)



discovery-service

```java
@EnableEurekaServer
```

![1560760752487](account-service/src/img/1560760752487.png)

gateway-service port:8765

```
@EnableZuulProxy
zuul:
  prefix: /api
  routes:
    account: 
      path: /account/**
      serviceId: account-service
    customer: 
      path: /customer/**
      serviceId: customer-service 
```

![1560760797848](account-service/src/img/1560760797848.png)

account-service port:2222

```java
@EnableDiscoveryClient
```

![1560760852549](account-service/src/img/1560760852549.png)

customer-service port:3333

```
@EnableDiscoveryClient
@EnableFeignClients
```

![1560761088109](account-service/src/img/1560761088109.png)

![1560761057136](account-service/src/img/1560761057136.png)

