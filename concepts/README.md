# ![RESTful Routing - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand what REST architecture is, and how it applies to routing. 

## What is REST

REST is an architectural style that provides standards for the relationship between the client and server ends of an application.

REST stands for REpresentational State Transfer. In order to break down what "Representational State Transfer" is, we'll need to first define what a *resource* is. From a REST standpoint, all content is considered a resource - data in a database, HTML pages, images, videos, etc. 

The "Representational" part of REST refers to the idea that, in response to a request from the client, a server will respond with a *representation* of the requested resource. Likewise, the client might pass a representation of a resource to the server, which the server can use to add data to, update, or delete data from a database.

If the client makes a request to get all of the posts in a blog, for example, they get back a representation of that resource in its current state. This data could be represented in various ways, although JSON or XML are the most common.

If adding a new post to a blog, the client passes a representation of the new resource to the server - the desired state for the resource - which can then be used to update the state of the database. 

This is the "State Transfer" part of REST, where the client and server transfer the state of resources between each other using representations of those resources. 

REST is not tied to a specific language or framework - again, it deals with representations of resources, not the resources themselves! Rather, it's an architectural style that guides the design principles of the internet. 

As a result, we describe systems that use this architecture as REST-compliant, or more commonly, as *RESTful*. 

## RESTful routing

As you might have guessed, "RESTful routing" is applying REST architecture to routing.

In REST, there is a clear separation between the client and server. The client sends requests to retrieve or modify resources, and the server sends responses to those requests. 

RESTful routes map the following HTTP verbs to [CRUD](https://developer.mozilla.org/en-US/docs/Glossary/CRUD) counterparts: 

POST - CREATE
GET - READ
PUT - UPDATE
DELETE - DELETE


## Why use RESTful routing conventions?

REST is a convention that makes your application predictable - it's a well understood architecture that other developers can easily adapt to and interpret. 