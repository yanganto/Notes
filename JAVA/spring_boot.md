# Spring Boot w/ Status checks
###### http://www.baeldung.com/spring-boot-actuators
###### https://www.youtube.com/watch?v=7L5rBQUMiPI
---
## Maven
```
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

## Gradle
```
    compile("org.springframework.boot:spring-boot-starter-actuator")
```


- this setting is not applied Chares project, with following error:
>Could not find org.springframework.boot:spring-boot-starter-actuator:.

---

## Application Info
  * /mappings - _use mappings to get follow uri_
  * /autoconfig
  * /beans
  * /configprops
  * /env
  * /info - _custumized applicaiton info_
  * /dump
  * /health
  * /metics
  * httpsessions.active **provid w/ Tomcat**
  * /trace - **Not** find out if any current existing_, recent complete request only
  * /shutdown - _need to be enabled_
shutdown endpoint source code
```
try {
  return SHUTDOWN_MESSAGE;
}
finally {
  new Thread(new Runnable() {

    @Override
    public void run() {
      try {
        Thread.sleep(500L);
      }
      catch (InterruptedException ex) {
        // Swallow exception and continue
      }
      ShutdownEndpoint.this.context.close();
    }

  }).start();
}
```


---

## Externalized Configurations
### properties file or YAML file
**/helth => /status**
```
endpoints.health.id=status
endpoints.health.sensitive=false
```

**enable shutdown**
```
endpoints.shutdown.enabled=true
endpoints.shutdown.sensitive=false
```

**:8080/status => :8081/check/health (localhost only and basic http auth)**
```
management.context-path=/check  
management.port=8081
management.address=127.0.0.1
management.security.enabled=true
security.basic.enabled=true
security.user.name=admin
security.user.password=password
```
security dependency: spring-boot-starter-security
all page with the same authorization
