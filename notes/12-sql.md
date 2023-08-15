# SQL

sql statements should have at the very end ;

dbSetup

CREATE TABLE 
capybaras(
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,  --------- Asign it an id, that increments 1 by 1 that are not the same
  name VARCHAR(10) NOT NULL COMMENT 'capybaras name',
  ownedByGrandma BOOLEAN DEFAULT true comment 'Owned By Grandma',
  birthday DATE NOT NULL,
  appleEaten SMALLINT UNSIGNED DEFAULT 0 ------ Watch for trailing commas, will break
)default charset utf8 COMMENT '';

ALTER TABLE capybaras
  ADD 
  livesAtFarm BOOLEAN NOT NULL DEFAULT FALSE;

DROP TABLE capybaras;

INSER INTO
 capybaras (name, ownedByGrandma, birthday, applesEaten)
 <!-- VALUES ('Cappy', true, '12-24-1990', 1000); ----------DATE has to be formatted specifically -->
 VALUES 
        ('Cappy', true, '1990-12-24', 1000)  ---This added a row to our database
        ('Tippy Toes', false, '2012-01-01', 3); --- This will add two rows at once

 SELECT name FROM capybaras;

 SELECT * FROM capybaras WHERE id = 2;

 SELECT * FROM capybaras WHERE applesEaten > 10;
 
 SELECT * FROM capybaras WHERE name LIKE '%tip%';

 DELETE FROM capybaras WHERE id = 2;


 <!-- SECTION Cars -->

 CREATE TABLE cars(
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT;
  make VARCHAR(255) NOT NULL,
  model VARCHAR(300) NOT NULL,
  color VARCHAR(100) DEFALUT 'BLUE' ,
  year SMALLINT UNSIGNED MAX 2024 MIN 1900 DEFAULT 1990,
  price DECIMAL MIN 1,
  ownedByGrandma BOOLEAN DEFAULT false
 )default charset UTF8 COMMENT '';

 <!-- appsetting.develment.json -->

 --in ScaleGrid-- 
 get master

 replace part of string with master
 username and password

 <!-- SECTION  -->

 <!-- Car.cs -->
    in public class Car 
    {
      prop -- auto complete


    }


    <!-- Repository -->

    private readonly IDBConnection _db; -- generate constructor with ctrl + .
<!-- write string of sql and give it to dapper to run -->

internal List<car> GetCars()
{
  string sql = "SELECT * FROM cars;";
  List<Car> cars = _db.Query<Car>(sql).ToList();

  return cars;

}

!! Dont forget to add services.AddScoped to Startup.cs !!

paramiterize data instead of ${} @carId

for things that dont result in null you need a ? in the model. for the value

then in the service you can use ??  in c# instead of a || like in js