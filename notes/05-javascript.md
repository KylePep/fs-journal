# JavaScript

New File
  app.js -- .js being javascript

  Script tag will go in the very bottom of the <body>
      <script src= "app.js"></script>

  You can use console.log to verify functionality console.log(js is working)
<!-- SECTION VARIABLES -->
  Industry standard to camelCase- this is lowercase word then Upper case word without a space

  delcare variable let, var, const
        let firstName = 'Kyle'

        Const lastName = 'Peppersack'
          cannot re assign to lastName because it is constant.
        
      Do not use
        Var bad
          out dated version of let

        Create new variable from two existing ones
          let fullName = firstName + lastName   --- You can add an empty string to create a space between firstName+ ' ' + lastName
          
        `` allow for string interpolation
        console.log(`This is the full name: ${fullName}`)
            ${} is what allows for variables to be called with in the string.

        You can utilize '' in the string by using "" instead.
        You can utilize "" in the string by using `` instead.

<!-- SECTION BOOLEANS -->
         let skyIsBlue = true
         skyIsBlue = false

          if(skyIsBlue) {              ----- This if statement will only perform the block if it is true, a false would cause it to exit.
            console.log('it is night')
          }
         
<!-- SECTION NUMBER -->

          let number = 3

          number + 1      ----result 3 because it does not report back to the variable.

          number ++      ---- result 4
          number = number + 3 result 6
          number +=2     ---- result 5

          Javascript uses PEMDAS  () - Parenthasis ^ - Exponents * - Multplication / - Division + - Addition - -Subtraction

<!-- SECTION OBJECT -->
        let dogName = 'Satch'
        let dogAge = '4'
        let dogIsHungry = false

          These can all be stored together as an object
          Adding information to ojbects requires key value pairs dogName is a key Satch is a value

        let dog = {
          dogName = 'Satch',
          dogAge = '4',
          dogIsHungry = false
        }
            console.log(dog.dogName) --- Satch
            console.log(dog['dogName']) -- Satch

        ** Objects in javaScript does not care about the order of key value pairs **

<!-- SECTION ARRAYS --> 
        let shoppingList = ['apple', 'bagel', 'salt', 'pepper']

 <!-- SECTION WEIRD STUFF -->
        let nothing = null
        let thing; --- returns undefined

<!-- SECTION FUCNTION -->
        function sayHello() {
          console.log('Hello Everybody, I am a function)
        }

        can call functions from the console ----sayHello()