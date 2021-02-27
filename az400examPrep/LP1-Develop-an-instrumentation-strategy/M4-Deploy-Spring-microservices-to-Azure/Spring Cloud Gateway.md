# Build a Spring Cloud Gateway

Gateways are used to route public HTTP traffic to microservices:

* They handle the routing logic.
* They secure the access to the microservices (which will not be publicly available).
* They can also have Quality of Service (QoS) capabilities, like doing HTTP rate limiting.

> curl https://start.spring.io/starter.tgz -d dependencies=cloud-gateway,cloud-eureka,cloud-config-client -d baseDir=todo-gateway -d bootVersion=2.3.6.RELEASE -d javaVersion=1.8 | tar -xzvf -

