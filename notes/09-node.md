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

  