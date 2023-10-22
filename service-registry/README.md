# Service Registry
spring-boot 3.x, maven, java 17

## Create new spring boot project `service-registry`
- Spring Web - `spring-boot-starter-web`
- Eureka Server - `spring-cloud-starter-netflix-eureka-server` 

### @EnableEurekaServer
- Add `@EnableEurekaServer` annotation to enable Eureka Server, by enabling this we are making it sure that this application will work as Eureka Server (service-registry).
- Add the port on which this server should run :
- This application is a server, we need to tell it not to connect to itself by adding some configurations in application.yml 