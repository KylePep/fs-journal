# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

    > Let, Var and const

02. What is the definition of a function?

    > functions are subprograms designed to perform a specific task.

03. What are the `SOLID` principles?

    > Single responsibility, Open and closed, Liskov Substitution, Interface Segregation and Dependency Inversion

04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    > let removePineapple = fruit.findIndex(fruitX => fruitX == 'pineapple' )
            fruit.splice(removePineapple,1)

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    > you.friends += them
        them.friends += you

06. Give an example of a JavaScript `Conditional`:

    > if else and else if

07. What is the main difference between `parameters` and `arguments`?

    > Parameters are variables used in a method declartion, arguments are the actual values used when the method is invoked
08. Instead of writing everything to the console, what is a better way to debug your code?

    > Using breakpoints to pause you code instead of the console.log

09. What is the difference between a `primitive` value and a `reference` value?

    > primitive are numbers and references are custom variables, strings

10. Demonstrate a loop that prints the numbers between -100 and 100?

    > for (i=-100, i < 99, i++)
        console.log(i)
