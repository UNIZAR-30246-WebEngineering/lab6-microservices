# Web Engineering 2020-2021 / Microservices

**In this assignment your PR must only modify the `README.md` file**.
Please, go to the [Wiki](https://github.com/UNIZAR-30246-WebEngineering/lab6-microservices/wiki) in order to get the instructions for this assignment.

## Primary goal

The code is based on the post [Microservices with Spring](https://spring.io/blog/2015/07/14/microservices-with-spring) developed by [Paul Chapman](https://spring.io/team/pchapman).
The laboratory shows a simple example of setting up a [microservices](http://martinfowler.com/articles/microservices.html) inspired system using Spring Boot and Eureka.
This project contains three apps:

* **Service discovery** (`registration`):
  It launches an open source  discovery server called [Eureka](https://github.com/Netflix/eureka) that will use the port 1111.
  The dashboard of the registration server is exposed in `http://localhost:1111`.
* **Microservice account service** (`accounts`):
  It is a standalone process that provides a RESTful server to a repository of accounts that will use the port 2222.
  What it makes special is that it registers itself to Eureka with the name `ACCOUNTS-SERVICE`.
  After launching this service you can see in the dashboard of Eureka that after a few seconds (10-20 secs) the `ACCOUNTS-SERVICE` service appears.
* **Microservice web service** (`web`):
  It is a standalone process that provides an MVC front-end to the application of accounts that will use the port 3333.
  What it makes special is that it registers itself to the Eureka with the name `WEB-SERVICE` and asks the Eureka where is the `ACCOUNTS-SERVICE`.
  Spring configures automatically an instance of `RestTemplate` for using the discovery service transparently!!!

This is a *NOT* a speed competition. The objective is to show that the following activities have been accomplished:

* The two microservices `accounts (2222)` and `web` are running and registered (two terminals, logs screenshots).
* The service registration service has these two microservices registered (a third terminal, dashboard screenshots)
* A second `accounts` microservice instance is started and will use the port 4444. This second `accounts (4444)` is also registered (a fourth terminal, log screenshots).
* What happens when you kill the microservice `accounts (2222)` and do requests to `web`?  
  Can the web service provide information about the accounts again? Why?

The above must be documented in a brief report (`report.md`) with screenshots describing what happens.

## Secondary goal (:gift:)

In progress:
* [Dockerize the three services](https://spring.io/guides/topicals/spring-boot-docker).

Proposed:

* [Circuit breaker for the requests from web to accounts that avoids a 500 error](https://spring.io/guides/gs/circuit-breaker/).
* [API gateway for web and registration](https://spring.io/guides/gs/routing-and-filtering/).
* [Centralized configuration for all microservices](https://spring.io/guides/gs/routing-and-filtering/).
* [Docker compose with scale by command line](https://thepracticaldeveloper.com/dockerize-spring-boot/).

Manifest your intention first by a PR updating this `README.md` with your goal.
If you desist of your goal, release it by a PR so other fellow can try it.

|NIA    | User name | Repo | Improvement | Score  
|-------|-----------|------|-------------|--------
| 760739 | [Alberto Calvo](https://github.com/AlbertoCalvoRubio) | [AlbertoCalvoRubio/lab6-microservices](https://github.com/AlbertoCalvoRubio/lab6-microservices/tree/test) | [Dockerize the three services](https://spring.io/guides/topicals/spring-boot-docker) | 