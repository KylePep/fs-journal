# Application Architecture, MVC Design Pattern
01. What are the Pillars of Object Oriented Programming (`OOP`)?
  
  > Encapsulation, Inheritance, Polymorphism
  Encapsulation - objects being devoted to a single task instead of everything
  Inheritance- properties of an object are passed down and do not need to be repeatedly initialized
  Polymorphism- treat the same object as different things depending on how it is needed at different times.

02. How does `export` differ from `export default`?
  
  > default exports export only a single object function or variable, a regular export can export multiple values

03. What is Encapsulation?
  
  > is walling of the parts of an applications that you do not wish to expose to the public interface.

04. What are some of the benefits of the `Proxy` object that we are using in our structure for applications?
  
  > Allowing an inbetween of user input and commands, to help keep certain parts of the application private, redirecting get commands for example.

05. What the difference between a `class` and an instance of a `class`?
  
  > class is the blueprint that a then instance of class is made from. the object is made from the class and instance describes their relationship

06. What is a computed Property?
  
  >an expression in brackets [], that will be computed and used as the property name.

07. What is the purpose of the `MVC` pattern?
  <!-- STUB -->
    Model: The Model handles data representation
    View: The View handles data visualization
    Controller: The Controller handles User Input and updates the View based on changes in the Model (🧠 brains of the operation)
  <!-- NOTE This may need expanding -->
  > The purpose of the `MVC` pattern is to keep everything organized...?
  and to keep aspects of the application encapsulated and therefor secure.

08. What is the job of the `Controller` in the `MVC` Pattern?
  
  > The controller updates the screen and handles user inputs

09. What is the job of the `Service` in `MVC`?
  
  > Service handles the mutation of values and writing directly to the AppState

10. What is the job of the `Model` in `MVC`?

   
  > the model is a blueprint for data in accross the application a fancy object