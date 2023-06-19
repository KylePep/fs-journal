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
