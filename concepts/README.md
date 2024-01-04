# ![RESTful Routing - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand what REST architecture is, and how it applies to routing. 

## What is REST

REST is an architectural style that provides standards for the relationship between the client and server ends of an application.

REST stands for REpresentational State Transfer. In order to break down what "Representational State Transfer" is, we'll need to first define what a *resource* is. From a REST standpoint, all content is considered a resource - data in a database, HTML pages, images, videos, etc. 

> 🧠 URL stands for Uniform Resource Locator - the path at which a resource can be located! 

The "Representational" part of REST refers to the idea that, in response to a request from the client, a server will respond with a *representation* of the requested resource. Likewise, the client might pass a representation of a resource to the server, which the server can use to add data to, update, or delete data from a database.

[tktk Hunter I think a good graphic would really make a difference in breaking up some of the more dense parts of this writeup. Either showing the flow of RESTful routing, or showing a resource and then it's representation as it arrives to the client, etc. ]

If the client makes a request to get all of the posts in a blog, for example, they get back a representation of that resource in its current state. This data could be represented in various ways, although JSON or XML are the most common. If adding a new post to a blog, the client passes a representation of the new resource to the server - the desired state for the resource - which can then be used to update the state of the database. 

This is the "State Transfer" part of REST, in which the client and server transfer the state of resources between each other using representations of those resources. 

REST is not tied to a specific language or framework - again, it deals with representations of resources, not the resources themselves! Rather, it's an architectural style that guides the design principles of the internet. 

As a result, we describe systems that use this architecture as REST-compliant, or more commonly, as *RESTful*. 

## RESTful routing

As you might have guessed, "RESTful routing" is applying REST architecture to routing.

In REST, there is a clear separation between the client and server. The client sends requests to retrieve or modify resources, and the server sends responses to those requests. 

In order to facilitate this, RESTful routes map HTTP verbs (get, post, put, and delete) to [CRUD](https://developer.mozilla.org/en-US/docs/Glossary/CRUD) counterparts: 

| HTTP Method | CRUD role | Purpose |
| -- | -- | -- |
| POST | CREATE | Adding a resource |
| GET | READ | Viewing a resource |
| PUT | UPDATE | Changing a resource |
| DELETE | DELETE | Removing a resource |

## Why use RESTful routing conventions?

REST is a convention that makes your application predictable - it's a well understood architecture that other developers can easily adapt to and interpret. REST is also designed around server-client separation, which helps with both scalability and flexibility as the client and server can be changed and expanded separately. 

As mentioned above, REST is also language agnostic - even as language or frameworks change, the communication between client and server stays the same! 

