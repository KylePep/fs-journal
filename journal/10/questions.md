# CSharp and SQL Fundamentals
01. What is the purpose of a `namespace`?

  > A namespace functions like javascripts import and export, allows code marked as public to be seen in and used in other parts of the application

02. What is the difference between a `class` and an `interface`?

  > a class has both a definition and an implementation whereas an interface only has a definition. ** may need to expand

03. What is the method that returns an instance of a class, yet it has no return type?

  > The contructor of a class

05. In the Car example what is the access modifier of the `Start()` method?

  ```c#
  abstract class Car
  {
    public string Start()
    {

      return "Vroooom";

    }
  }
  ```

  > The access modifier is public, making it accessible for all classes

06. In the Car example what is `string` an indication of?

  > String is an indication of its Type

07. In the Car example what is `abstract` preventing?

  > abstract is preventing the class from being fully implemented ** may need to expand

08. In a SQL table, what is the difference between information in a row and information in a column?

  > columns are the different keys or attribute data is organized by, the rows are the actual peices of data with all of those value pairs

09. Demonstrate the necessary SQL for creating a table called `characters` with the values `name, age, description` as strings, and an `int` id.

  >  CREATE TABLE characters(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    age VARCHAR(255) NOT NULL,
    description VARCHAR(255) NOT NULL,
    Age SMALLINT UNSIGNED
 )default charset UTF8 COMMENT '';

10. In SQL how can you query more than a single table? Provide an example.

  > SELECT name FROM capybaras, cars;
