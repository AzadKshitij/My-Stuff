# 1. CQRS design patterns
## Problem Statement
- Some time we just have many users subscribed to our service and we write on the same database as we are reading it may affect the speed and not all the users will get the updated data in real-time.
- Managing security and permissions can become complex, because each entity is subject to both read and write operations, which might expose data in the wrong context.
- There is often a mismatch between the read and write representations of the data, such as additional columns or properties that must be updated correctly even though they aren't required as part of an operation.
- **Answer: -**  How to implement a query that retrieves data from multiple services in a microservice architecture?

## Context
In traditional architectures, the same data model is used to query and update a database. That's simple and works well for basic CRUD operations. In more complex applications, however, this approach can become unwieldy. For example, on the read side, the application may perform many different queries, returning data transfer objects (DTOs) with different shapes. Object mapping can become complicated. On the write side, the model may implement complex validation and business logic. As a result, you can end up with an overly complex model that does too much. Some time we just have many users subscribed to our service and we write on the same database as we are reading it may affect the speed and not all the users will get the updated data in real-time.

**Answer:** -   You've used the Database per service and Microservices architectural patterns. Consequently, it is more difficult to build queries that combine data from many providers. Additionally, the data can no longer be easily retrieved if the Event Sourcing pattern has been used.

## Forces/Constraints
**Answer:** - For simple CRUD operation we don't need different databases for reading and writing. Implementing CQRS pattern may slow down your development of your simple application. It requires expertise in a variety of database technologies. It gets hard to manage as the size of database increases. As there are different databases for writing and reading out cost of hosting the database increase by a lot. Consistency within the database is hard to manage. As there are more databases the probability of failing a database increases. 

## Solutions
Give an explanation of a view database, a read-only replica created to accommodate that query. By listening to Domain events released by the service that owns the data, the application maintains the replica current with the data.







# 2. Saga Design Patterns


## Problem Statement
- **Answer: -**  How to implement complete video uploading system?

## Context

**Answer:** -   Each service has its own database. Some upload services span multiple service so we need a mechanism to implement uploader that span services. 

## Forces/Constraints
**Answer:** -   2 Phase Commit is not an option as it is more complex and time consuming. AS it is managed globally if that main element fails our whole service will fail.

## Solutions
- A saga is a sequence of local transactions. Each local transaction updates the database and publishes a message or event to trigger the next local transaction in the saga. If a local transaction fails because it violates a business rule then the saga executes a series of compensating transactions that undo the changes that were made by the preceding local transactions. 
`

live       -|-----
              |       |
video    -|--------- Description ------ Publish
              |       |
shorts   -|-----

After every stage save the active stage so we will not loos any data.









