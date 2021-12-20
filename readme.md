# fmchan Microservices

All the codes refer to this tutorial: [javatpoint](https://www.javatpoint.com/microservices)

## You will learn
- Establishing Communication between Microservices
- Centralized Microservice Configuration with Spring Cloud Config Server
- Using Spring Cloud Bus to exchange messages about Configuration updates
- Simplify communication with other Microservices using Feign REST Client
- Implement client side load balancing with Ribbon
- Implement dynamic scaling using Eureka Naming Server and Ribbon
- Implement API Gateway with Zuul
- Implement Distributed tracing with Spring Cloud Sleuth and Zipkin
- Implement Fault Tolerance with Zipkin

## Ports

|     Application       |     Port          |
| ------------- | ------------- |
| Limits Service | 8080, 8081, ... |
| Spring Cloud Config Server | 8888 |
|  |  |
| Currency Exchange Service | 8000, 8001, 8002, ..  |
| Currency Conversion Service | 8100, 8101, 8102, ... |
| Netflix Eureka Naming Server | 8761 |
| Netflix Zuul API Gateway Server | 8765 |
| Zipkin Distributed Tracing Server | 9411 |

### To run app with different port
- allow "Multiple instance"
- add "VM Options"
- input ```-Dserver.port=``` to VM argument

## Remark Links
- Check config:
    - http://localhost:8888/limits-service/default
    - http://localhost:8888/limits-service/qa
- Fetch properties:
    - http://localhost:8080/limits
    - http://localhost:8081/limits
- Refresh Bus:
    - POST http://localhost:8080/actuator/bus-refresh

- Netflix Eureka Naming Server: http://localhost:8761/
- Zipkin distributed Tracing Server: http://localhost:9411/zipkin/
- RabbitMQ message broker: http://localhost:15672/

- H2 database: http://localhost:8000/h2-console
- Restful Api (currency-exchange):
    - http://localhost:8000/currency-exchange/from/AUD/to/INR
    - http://localhost:8001/currency-exchange/from/AUD/to/INR

- currency-converter API:
    - Traditional: http://localhost:8100/currency-converter/from/USD/to/INR/quantity/1000
    - Feign: http://localhost:8100/currency-converter-feign/from/USD/to/INR/quantity/1000

- Netflix Zuul API gateway Server:
    - http://localhost:8765/currency-exchange-service/currency-exchange/from/EUR/to/INR
    - http://localhost:8765/currency-conversion-service/currency-converter-feign/from/USD/to/INR/quantity/100

- fault-tolerance: http://localhost:8081/fault-tolerance-example

## Environment
- JDK 1.8
- Spring Boot 2.0.0.RELEASE
- Maven 4.0