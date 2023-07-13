# Node

Node is a javascript runtime enviroment

node-server-auth0

Inside server -> main -> comment out DbConnection.connect()
We are not connecting to a database

Inside server -> Startup -> comment out Auth0 - audience and its ({})

spinnning up server with the run debug button

Postman is an application that mocks a client and can interact with your Api

express-mvc

.env -------------should never be pushed up to github

  connection_string ============ mongodb -> connect -> drivers -> connection string
                        replace <password> with mongodb -> database access -> edit auto generate -> copy and replace including the <>
  Port ======== not necessary at this time
  AUTH_DOMAIN  ============= autho -> applications -> my app -> domian
  AUTH_AUDIENCE ============= auto -> applications -> api
  AUTH_API  ============= autho -> applications -> my app -> api

  copy and paste this from the .env to the env.js

  bcw serve from the client folder

  slack .env contents to yourself once you established the connection
  
  -these are all delcared within the controllers constructor, they are functions that the client takes advantage of to interact with the api-
  -inside the '' is where a parameter is specified like '/:id', used later to find specific objects in the api
  -the this.xyz is calling down to a function that exists inside the controller. these function the same way normal functions within the mvc    template function

  .get('',this.getApiObject)
  .post()
  .delete()
  .put()
  
  **inside the controller**
  async getApiObject(req, res, next) { ----- req res next are essential, in that order req is the request from the client, res is the response and next is the error catch
    try {
      const object = await objectServices.getApiOjbect()
      res.send(objects)

    } catch(error) {
      next(error)
    }
  }
  **inside the service** 
  async getApiOjbect(){
    const objects = await dbContext.Objects.find()  ----This looks for all of the objects with the api ojbects collection
    reutrn objects ----this returns objects back up to the controller so they can be sent in the response.
  }



  mongoose has its own functions used to interact with the api

  .find() - returns an array of everything in the database, a filter can be passed to it

  .findById() this method will return one item from the database collection that has the _id passed in. Specifically _id. it is very particular

  .create() this method will insert an entry into the given collection and return the instance of the item

  .save() invoked from an object pulled from the database. if any values from the object were changed, this will save those changes to the database.

  .remove() invoked from an object pulled from the database. this will remove the item from the database.

UML unified modeling language

