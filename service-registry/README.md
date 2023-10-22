# Service Registry
spring-boot 3.x, maven, java 17

## Create new spring boot project `service-registry`
With following dependencies:-
- Spring Web - `spring-boot-starter-web`
- Eureka Server - `spring-cloud-starter-netflix-eureka-server` 

### @EnableEurekaServer
- Add `@EnableEurekaServer` annotation to enable Eureka Server, by enabling this we are making it sure that this application will work as Eureka Server (service-registry).
- Add the port on which this server should run : `8761`
- This application is a server, we need to tell it not to connect to itself by adding some configurations in application.yml 

```yaml
# application.yml

spring:
  main:
    banner-mode: "off"

logging:
  pattern:
    file: "%d{dd-MM HH:mm} - %-5level - %logger{1} - %msg%n"
  level:
    root: INFO

# Service registry settings
server:
  port: 8761
eureka:
  instance:
    hostname: localhost
  client:
    register-with-eureka: false
    fetch-registry: false
    serviceUrl:
      defaultZone: http://${eureka.instance.hostname}:${server.port}/eureka/


  
```