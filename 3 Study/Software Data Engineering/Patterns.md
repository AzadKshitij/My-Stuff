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

# MVC 
![[Assets/Pasted image 20220831132845.png]]

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