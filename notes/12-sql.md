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

<!-- Full Stack -->

Fill out the appsettings.Development.json -- also copy it from graigslist and send it to myself using slack

Fill out env.js --- save this too

Verify Log in --- Get bearer token
--Failed
change the baseUrl to the correct 7045 instead of 3000
--Still Faied
needs an s - https://localhost7045

Creating Table
** SQL ENUM **
    category Enum('misc','cats','dogs','games','gachamn') Default 'misc',
** SQL Creator Id **  
  creatorId VARCHAR(255) NOT NULL, --- Thats it for now
** Foreign Key ** 
  FOREIGN KEY(creatorId) REFERENCES accounts(id) 
  FOREIGN KEY(creatorId) REFERENCES accounts(id) ON DELETE CASCADE -- When the account is deleted, it deletes all of the would be orphan data.

!! Floating executes are bad. If you see an execute in the middle of a block, thats a problem !!


** Repository CreatorID **

Needs to create a new private read only in the controller, that connects it to the Auth0Provider
(Ctr + .) -- Add parameters, adds it to the existing service call

Need to async await the method

Wrap the ActionResult<> in Task<>

** Auth Decorator **
[Authorize] applys to the first method right beneath it. Requires Log in 
[httpPost]


SELECT 
album *,
account*
FROM albums
JOIN accounts
ON accounts.id = album.creatorId;

------------------I wasn't paying attention for the first bit of this, I believe it was a profile built into account and profile built onto album

Select
alb.*,
acc.*
FROM albums alb
JOIN accounts acc ON acc.id = alb.creatorId

LIST<Album> albums = _db.Query<Album, Profile, Album>(
  sql,
  (album, profile) => {
    album.Creator = profile;
    return album; 
  }
).ToList();
return albums;

added profile to class
public Profile Creator { get; set; }

Profile its self was build as a public class on account

public class Profile {

}


<!-- SECTION Many to Many -->
Table refrences the two different Ids from the two different Tables with the foreign key they are referencing, with an ON DELETE CASCADE also.

<!-- Data Model -->
-Id-- int
-AlbumId -- int
-AccountId -- string

Create new class inside of Collabortor Model

<!-- Theres a better way -->
public class ProfileCollaboration
{
  int CollaborationId
  +
  Everything from profile
}
<!-- Better way -->
public class ProfileCollaboration : Profile
{
  int CollaborationId
  <!-- The profile inheritence will bring in everything that was otherwise typed out. -->
  <!-- +
  Everything from profile -->
}

public class Account : Profile
{
  public String Email {get; Set;}
  inherits all of the same stuff from Profile
}

<!-- Controller -->
[Post]
-With Auth-
-Same-

--Starting in ablums controller
[HttpGet ("{albumId}/collaborators")]
public ActionResult<List<ProfileCollaboration>> GetcollaboratorsByAlbumId(int albumId)
{
  trycatch
  {
    List<ProfileCollaboration>
  }
}

[HttpGet ("{albumId}/collaborators")]
public ActionResult<List<Collaborator>> GetcollaboratorsByAlbumId(int albumId)
{
  trycatch
  {
    List<Collaborators>
  }
}


<!-- Service -->
[Post]
-Same-

[GET]
-Send to repository

<!-- Repository -->
[Post]
Frankenstein
-int cId = _db.Executescalar<int>(sql, cData)
cData.id = cId
return cData

[GET]
string sql = @"
SELECT
*
FROM collaborators
WHERE id = @albumId
;";

List<Collaborator> collaborators = _db.Query<Collaborator>(sql, new{albumId}).ToList();
return collaborators;
sql = @"
SELECT
collab.*,
acc.*
FROM collaborators collab
JOIN accounts acc ON acc.id = collab.accountId
WHERE collab.albumId = @albumId
;";

LIST<ProfileCollaboration> collaborators = _db.Query<Collaborator, ProfileCollaboration, ProfileCollaboration>(
  sql,
  (collaborator, profile)=>
  {
    profile.collaborationId = collaborator.Id
    return profile;
  },
  new {albumId}).ToList();
  
  return collaborators;


<!-- Next get -->

public class AblumCollaboration : Album
{
  public int collaborationId {get; set;}
}

-Starting in account controller-

[Auth]
[Get]
public async Task<ActionResult<List<AlbumCollaboration>>> GetMyAlbumCollaborations()
{
  -trycatch-
  Account UserInfo = await _authstuff
  List<AlbumCollaboration> collaborators = _collaboratorsService.GetMyAlbumCollaborations(UserInfo.Id);
}

-In Collaborators Service-

-Same-

-In Collaborators Repository-

sting sql = @"
SELECT
collab.*,
alb.*
FROM collaborators collab
JOIN albums alb ON alb.id = collab.albumId
WHERE collab.accountId = @userId
;";

List<AlbumCollaboration> collaborators = _db.Query<Collaborator, AlbumCollaboration, AlbumCollaboration>(
  sql,
  (collaborator, album)=>
  {
    album.CollaborationId = collaborator.Id;
    return album;
  },
new {userId}).ToList();

return collaboratrors;
