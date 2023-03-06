#What are microservices?

Microservices are independently releasable services that are modelled around a business domain. 
A service encapsulates functionality and makes it available to other services via networks. 
The microservice architecture avoids the use of shared database in most circumstances and instead implement their own data storage where needed.
Microservices embrace the concept of information hiding: hiding as much information as possible inside a component and exposing as little as possible via external interfaces.

> Note: Hexagonal Architecture pattern. This pattern describes the importance of removing the business logic from the external interfaces(available to the user). In code, this would
typically mean that controllers should be the external points to users, where as services and service logic should be seperated by using interfaces.

<h4> Key concepts of microservices </h4>

<h5> Independent deployability </h5>

We can make a change to a microservice, deploy it and release that change to our users without having to re/deploy any other microservices.
To ensure this is possible, the services must be loosely coupled.

<h5> Modeled around a business domain </h5>

Make cross-service changes as infrequent as possible. Seperate logic between presentation layer, business logic layer and data layer.

<h5> Owning their own state </h5>

Databases should NOT be shared between services. In the case that a microservice wants to get data held by another service, it must go and ask that microservice for the data.
Limiting backward-incompatible changes to microservices. (previous versions not working with newer versions).

<h5> Size </h5>

Size is not really important in terms of microservices. Focus on one microservice at a time and with time add more microservices.

<h3> The Monolith </h3>

All of the code is packed in a single process. Sometimes, multiple instances of the same monolith may be deployed for scalability purposes. Microservices are not always the option - monoliths are suitable at times as well.

<h5> The modular monolith </h5>

The single process is seperated into different modules. Each modules can be worked on individually, but they are still dependend on eachother.
Shopify is an example of a company that uses the modular monolith architecture. 
A modular monolith can also have multiple database instances for different sorts of data. 

<h3> Advantages of monoliths </h3> 

Easier developer workflows, easier deployment. Usually, monolith architecture is the first choice to come to mind when thinking of developing software, even though it is "legacy" at this point.

> Note: As the amount of services increase within the system, managing it becomes quite difficult. To deal with this, a simple log aggregation system is a must for adoping the microservice architecture.
> Some products to mention: Lightstep and Honeycomb. They represent a set of new tools that allow easy monitoring and tracking.

<h5> Containers and kubernetes <h5>

Each service should be run in isolation. Containers provide a lightweight way to create isolated execution for service instances. Kubernetes offer the tools to manage all of the containers and the amount of resources they use up.

<h5> Streaming </h5>

How do we share data between services? One of the most popular choices for most people is Apache Kafka for streaming data in a microservice environment.
Kafka offers the ability to process large volumes of messages.

<h3> Advantages of Microservices </h3>

- The ability of using different technologies for each service. Also, different types of storage can be used for different types of services. For example, authentication can be build with Golang, but the rest with .NET C#.

- Robustness. In the case that one component fails, it does not create a domino effect where it takes down the rest of the system with it.

- Scalability. 