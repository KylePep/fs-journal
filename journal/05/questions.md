# Intro to Server side concerns with JavaScript
01. What do the letters of the acronym `CRUD` stand for?

  > Create, Read, Update, Delete

02. Each action that `CRUD` represents maps to an HTTP request. What HTTP request does each `CRUD` action correspond to?

  > Create - Post, Read - Get, Update - Put, Delete - Delete

03. What does `ORM` stand for? Which `ORM` do we use when interacting with MongoDB

  > Object-relational mapping, Mongoose

04. Which two `HTTP` request types include a body?

  > Create and Update

05. In a/an _______ coding model, when you call a function, it returns only when the action has finished and stops your program for the time the action takes. Likewise in a/an _______ coding model, multiple things are allowed to happen at one time. When you perform an action, your program continues to run.  Fill in the blanks.

  > 1- Asynchronous, 2- Synchronous

06. What are the three types of data relationships? Provide an example of each.

  > 1:1 one to one- there is one lock for one key and one key for one lock, 1:N one to many - there are many cds to one cd player there is only one cd player to many cds, N:M many to many - there are many actors to many movies

07. What is middleware?

  > middleware is software that different applications use to communicate with each other. Like a middleman, helps make the information useable by the other -- mongoose

08. The ______ pipeline delivers information from the client while the ______ pipeline returns it. Fill in the blanks. 

  > request pipeline and response pipeline

09. Demonstrate the pattern that is used to include a request query with the client's `HTTP` request providing the property `tag` and the value `winter`.

  > http://localhost:3000/api/seasons/winter

10. What is a ***virtual property***?

  > a virtual property is a property that establishes a relationship with one part of the database to another part of the database
