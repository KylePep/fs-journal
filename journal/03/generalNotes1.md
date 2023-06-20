<!-- STUB -------MVC? -->
Is MVC a method of building out multiples of an object, IE creating many cards or clickable (purchasable) Store items?


<!-- NOTE this is ES6 -->
<!--STUB ----My response after the lecture--------->
math.js
------
let sumAll = (a, b) => {return a + b;}
let subtractAll = (a, b) => {return a - b;}
let divideAll = (a, b) => {return a / b;}
let multiplyAll = (a, b) => {return a * b;}
let findModulus = (a, b) => {return a % b;}
<!-- Export using, This makes it exposed -->
export {sumAll, subtractAll, divideAll, multiplyAll, findModulus};
------


app.js
------
import {sumAll, subtractAll, divideAll} *from* './math.js';

<!-- Import as an alias -->
<!-- * means all in this syntax, so import all from math -->
import * as math from './math.js';
<!-- You can then use the imported module -->
console.log(math.sumAll(50, 10)); // 60
console.log(math.subtractAll(50, 10)); // 40
console.log(math.multiplyAll(50, 10)); // 500
console.log(math.divideAll(50, 10)); // 5
console.log(math.findModulus(50, 15)); // 5
-----

// Classes are fancy objects
// Organization, structure
<!-- no more mkdir -->
command promt

<!-- NOTE don't code along, Maybe tiny bits of code -->

bcw create ------------------Do this with the file destination ie, 2023 - week 3 then bcw create
  mvc --------This week
    Project name: -name----- pingPong
    Initialize git (n) ---- may be easier to do it with VSCode
    <!-- bcw create, mvc creates an butt load of files and folders -->

    type="module" ---- this enables import and export
    using classes, constructors and new to build out fancy objects this week.

    Global variables are going to go in AppState.js within the class ObservableAppState block

<!-- NOTE  Whenever possible use intellicense to create the import function-->
    import {variable} from "xyz.js"
  If you bet an error 404 you might be missing a .js somewhere

  export function sayHello(){
    console.log('helloWorld')
  }

  import |above|

  Classes - big fancy object, Good intellicense, Store functions, export classes out, Bundle like things together and send it.-

  Method is a function written inside of an object

  MVC follows V -view, C -controller, S- Service, M- models flow

  The service is the only thing that can change out values***  Call a change in values

  Controller talks to the Service for the sake of security

  Pop is prebuilt sweet alerts

  Ctrl+P will let you search your files

  <!-- creating a controller -->
  add it to the controllers folder, PlayerController.js   --------------In JavaScript new classes are Capitilized pascall case

  <!-- STUB PLAYERCONTROLLER -->
<!-- controllers should start with export -->
export class PlayersController{
  <!-- constructor will run code the way weve been calling functions at the bottom of the js -->
  constructor(){
    console.log('Players Controller Loaded');
  }
}

Controllers should be loaded from the router
controllers: PlayersController ---- this should try to auto complete with the import function

<!-- STUB PLAYERCONTROLLER -->
export class PlayersController{

  constructor(){
    console.log('Players Controller Loaded');
  }

  <!-- NOTE public methods accessible to the user -->
  
  sayHello(){
    console.log('button works')
    console.log('test small!')
  }

}

app.PlayersController.sayHello() ---- is how you would call this from the main > div > button
<!-- STUB player.js -->
create a model, models folder Player.js

starting with an export class Player {

  contructor(name){  ---- constructors can have parameters
    <!-- this is a reserved word -->
    debugger---------------------------------------------------------debugger will pull up the debug window and let step through line by line
    this.score = 0
    this.name = name
  }

}
<!-- STUB AppState.js -->

AppState.js-----------

set up property on the app state

players = [
  new Player('Batman'),   ----Still need to import----
  new Player('Robin'),
]

<!-- STUB player.js -->
create a model, models folder Player.js

export class Player {

  contructor(name, imageUrl){  ---- constructors can have parameters
    this.score = 0
    this.name = name
    this.imgUrl = imageUrl
  }

}

<!-- STUB AppState.js -->

AppState.js-----------

set up property on the app state

players = [
  new Player('Batman', 'imageUrl'),   ----Still need to import----
  new Player('Robin','imageUrl'),
]

<!-- STUB PLAYERCONTROLLER -->
<!-- Controller updates the view -->

<!-- NOTE private functions inaccessible to the user -->
funtion _drawPlayers() {   ----------------Underscores are industry standard for private functions
  console.log('Draw players works?')
  let players =  AppState.players
<!-- util Writer -->
  setHTML('players',players[0].PlayerCardTemplate)--------------------------------------------Needs import

}


export class PlayersController{

  constructor(){
    console.log('Players Controller Loaded');
    _drawPlayers()
  }

  <!-- NOTE public methods accessible to the user -->
  sayHello(){
    console.log('button works')
    console.log('test small!')
  }

}

<!-- NOTE  GETTERS-->
getters
getters must return a value
getters do not take in any parameters

get PlayerDetails(){
  let details = `Hello, my name is ${this.name} and my score is ${this.score}`

  return details
}

get PlayerCardTemplate(){
  return /*html*/ `                 /*html*/ will make it look like html
      html div template
      `picture source ${this.imgURL}`
  `
}

<!-- NOTE make a service inside services -->
PlayersService.js

class PlayersService{

<!-- NOTE services do not generally have a constructor -->
}

<!-- NOTE singleton -->
export const playerService = new PlayersService()

<!--  -->
app.playersController.increasePlayerScore