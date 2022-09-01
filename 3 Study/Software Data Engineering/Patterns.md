---
tags: []
---
# Architectural Pattern
A general, reusable solution to a commonly occurring problem in software
architecture within a given context.
# Layered Pattern
1. Organize the components of an application into horizontal logical layers and physical tiers.
2. A higher layer can use services in a lower layer, but not the other way around.

![[Assets/Pasted image 20220829181354.png]]

![[Assets/Pasted image 20220831085743.png]]

![[Assets/Pasted image 20220831085814.png]]

![[Assets/Pasted image 20220831085936.png]]

### How to plan for a Layered System?

1. Group functionalities specific to one aspect of the system
	(Presentation <> Business <> Services <> Data)
	• Decide the names and number of layers
2. How big the layers will be
	Develop the layers and decide which ones will be open.
	Functionalities that will be exposed to the rest of the system
	API of the layer.
3. Messaging mechanism between layers 
4. Communication model (the flow of the request)
	Top-Down approach
	Make some layers cacheable?

### Advantages and Limitations:
1. Advantages:
	Separation of concerns
	Layers of isolation
	Ease of testing
	Ease of development
2. Limitations:
	Lack of agility
	Difficulty of deployment
	Low performance

### Pitfalls to watch out for:
	Creating more layers than is necessary.
	Layers that don't add any value to the request or response.
# Broker Pattern
1. The Broker architectural pattern can be used to structure distributed software systems with decoupled components that interact by remote service invocations.
2. The Broker component is responsible for coordinating communication, such as forwarding requests, as well as transmitting results and exceptions.

![[Assets/Pasted image 20220829181559.png]]

# Pattern: Monolithic Architecture
## Context
You are developing a server-side enterprise application. It must support a variety of different clients including desktop browsers, mobile browsers and native mobile applications. The application might also expose an API for 3rd parties to consume. It might also integrate with other applications via either web services or a message broker. The application handles requests (HTTP requests and messages) by executing business logic; accessing a database; exchanging messages with other systems; and returning a HTML/JSON/XML response. There are logical components corresponding to different functional areas of the application.

## Problem
What’s the application’s deployment architecture?

## Forces
- There is a team of developers working on the application
- New team members must quickly become productive
- The application must be easy to understand and modify
- You want to practice continuous deployment of the application
- You must run multiple instances of the application on multiple machines in order to satisfy scalability and availability requirements
- You want to take advantage of emerging technologies (frameworks, programming languages, etc)

## Solution
Build an application with a monolithic architecture. For example:

- a single Java WAR file.
- a single directory hierarchy of Rails or NodeJS code

# MVC (Separation of concerns)
![[Assets/Pasted image 20220831132845.png]]

![[Assets/Pasted image 20220901155818.png]]

# Pipe and Filter
- Filters are reusable (not need to be).
- Advantage of Concurrency.
- 
![[Assets/Pasted image 20220901160052.png]]

# Client and Server
## 1. Clients
- A client can be a machine or a program
- A client machine: computer, laptop, mobile etc.
- A client program: A client program is a program that allows the user to make requests. Ex: Browser, online support.
- A client, whether it is a machine or a program, is an appliance and a way to make requests through the web.
## 2. Server
- A server is a computer program NOT a Device 
- High-Performance computers are called servers because they run server programs
- Servers provide functionality and serve other programs called clients.
- A single server can serve multiple clients at the same time. 
- We can run multiple servers on one single machine, they are called virtual servers
- A server can contain web resources, host web applications, stores User and program data, etc.
- It is used to serve hundreds or thousands of clients. 
- A server is always listening for requests, and as soon as if receives one, responds with a message.
- The client-server model is just one way for the computers to communicate via the web
- The client-server is based on a centralized structure
- There is another way to communicate via a decentralized structure
- It Is The Peer—To-Peer Model

# P2P Model
- There is no client and no server.
- Both computers can be requesters and response providers
- Each one is able to send and receive data directly with one another

# Service-Oriented Architecture (SOA)
Definition:: Service-Oriented Architecture (SOA) is a stage in the evolution of application development and/or integration. It defines a way to make software components reusable using the interfaces. 
![[Assets/Pasted image 20220901173342.png]]
![[Assets/Pasted image 20220901173416.png]]


Formally, SOA is an architectural approach in which applications make use of services available in the network. In this architecture, services are provided to form applications, through a network call over the internet. It uses common communication standards to speed up and streamline the service integrations in applications. Each service in SOA is a complete business function in itself. The services are published in such a way that it makes it easy for the developers to assemble their apps using those services. Note that SOA is different from microservice architecture.

-   SOA allows users to combine a large number of facilities from existing services to form applications.
-   SOA encompasses a set of design principles that structure system development and provide means for integrating components into a coherent and decentralized system.
-   SOA-based computing packages functionalities into a set of interoperable services, which can be integrated into different software systems belonging to separate business domains.

There are two major roles within Service-oriented Architecture: 

1.  **Service provider:** The service provider is the maintainer of the service and the organization that makes available one or more services for others to use. To advertise services, the provider can publish them in a registry, together with a service contract that specifies the nature of the service, how to use it, the requirements for the service, and the fees charged.
2.  **Service consumer:** The service consumer can locate the service metadata in the registry and develop the required client components to bind and use the service.

# Pub-Sub
![[Assets/Pasted image 20220901173859.png]]
![[Assets/Pasted image 20220901173918.png]]
![[Assets/Pasted image 20220901174033.png]]

# Shared Data Software Architecture
- Data-centered software architecture is characterized by a centralized data store that is shared by all surrounding software components.

# 4+1 Views 
![[Assets/Pasted image 20220901174458.png]]
# Microservice Architecture
Definition:: Micro Service is an architecture that allows the developers to develop and deploy services independently. Each service running has its own process and this achieves the lightweight model to support business applications.
## Pros
- Highly maintainable and testable
- Loosely coupled
- Independently deployable
- Organized around business capabilities
- Owned by a small team

![[Assets/Pasted image 20220829182231.png]]

![[Assets/Pasted image 20220829182307.png]]

## The pattern language is your guide

- The microservice architecture is not a silver bullet. It has several drawbacks. Moreover, when using this architecture there are numerous issues that you must address.
- The microservice architecture pattern language is a collection of patterns for applying the microservice architecture. It has two goals:

1. The pattern language enables you to decide whether microservices are a good fit for your application.
2. The pattern language enables you to use the microservice architecture successfully.