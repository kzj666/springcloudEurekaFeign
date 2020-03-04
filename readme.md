#Feign
##1.导入依赖
```xml
<!--Feign的依赖-->
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-feign</artifactId>
    <version>1.4.6.RELEASE</version>
</dependency>
```

##2.在service接口上加上@FeignClient注解，加上@Component注解，将该接口放入容器
@FeignClient(value = "SPRINGCLOUD-PROVIDER-DEPT")，value是微服务的名字


##3.在客户端注入该接口对象，利用该对象调用接口内的方法，当客户端请求（/consumer/dept/list），调用接口方法，就会请求接口上对应的@RequestMapping请求（/dept/list），再被服务端捕获执行


##4.在客户端的主程序类上加上注解@EnableFeignClients
@EnableFeignClients(basePackages = {"com.common.springcloud"})