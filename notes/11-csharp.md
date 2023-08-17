# CSharp

Do not kabob-case file names, use camelCase or snake_case

in command
  dot net new console

code .

Program.cs

say yes to add stuff if it pops up

Console.WriteLine("Hellom World!")

const let and var don't work in c# 

string name = 'Kyle'  --- This is an error needs "for strings with more than one character"
string name = "Kyle"   --- needs ;

string firstName = "Kyle";
char middleInitial = "R";
string lastName = "Peppersack";

Console.WriteLine("${This doesnt work}");
Console.WriteLine($"Hello, my full name is {firstName} {middleInitial} {lastName}");
Console.WriteLine($"Hello, my full name is {firstName.ToUpper()} {middleInitial} {lastName}");

int num = 3;  numbers are intigers

int halfNum = 2.5; --- this is an error

(int are whole numbers)
(double is for a number with decimal point)

double halfNum = 2.5;

double total = num + halfNum;

Console.WriteLine(num + halfNum);

bool kyleLikesDbz = true;

if(kyleLikesDbz)
{
  Console.writeLine("Of course this is true");
}

--Truthy falsey does not exist in javascript--
=== does not work in c#

if(firstName) -- this would be truthy in js, will not work in c#
{
  --writeLine--;
}

if(firstName == "Banana") 
{
  --writeLine--;
}


int [] numbers = {1,2,3,4,5};

for(int i = 0; i < numbers.length; i++)
{
  int number = numbers[i];
  Console.WriteLine(number);
}
Arrays suck in c#

Generally use Lists

List<String> names = new List<sting>();

names.Add("Batman");
names.Add("Robin");
names.Add("Ivy")
names.Remove("Ivy");

foreach(string name in names)
{
  Console.WriteLine($" My name is {name}")
}



bcw Create dotnet-auth
comment line in Startup.cs - cats_api_csharp for reference

namespace ... With name space being used in a given file it'll be accessible to other files using the same namespace

right click new new C# class

Cat.cs

namespace cats_api_csharp.Models;

public class Cat
{
  ---Code snippet prop ---
  public string Name { get; set; }

  public int Age { get; set; }

  public bool HasTail { get; set; }

  public double NumberOfLegs { get; set; }

  <!-- Constructor -->
  <!--  -->
  public Cat(string name, int age, bool hasTail, double numberOfLegs) 
  {
      Name = name;
      Age = age;
      HasTail = hasTail;
      NumberOfLegs = numberOflegs;
  }
}

<!--  -->
new c# ApiController -- CatsController.cs

[Route("api/[Controller]")]
this takes CatsController and puts !cats!(Controller) in lower case and replaces Controller

localhost7045
need to continue past error
url/swagger will take you to automatic breakdown of api or link

public class CatsController : ControllerBase
{

  private readonly CatsService _catsService; --- ctrl + dot => can auto genterate line 136-139

  public CatsController(CatsService catsService)
  {
    _catsService = catsService;
  }


  [HttpGet]
  public ActionResult<List<Cat>> GetCats()  -- ActionResult is what allows Ok and BadRequest to happen or be accessible
  {
    try
    {
      List <Cat> cats = _catsService.GetCats()
      return Ok();
    }
    catch(Exception e)
    {

      return BadRequest(e.Message);
    }
  }
}

<!--  -->
New Class CatsService

public class CatsService
{

  private readonly CatsRepository _catsRepository; crl+. generate

  internal List<Cat> getCats()
  {
    List<Cat> cats = _catsRepository.GetCats()
    {
    return cats;
    }
  }
}

<!-- -->
New Class CatsRepository

public class CatsRepository
{
  private readonly List<Cat> Cats = new List<Cat>();
}

Error Dependency Injection

Startup.cs -- needs to build the service and repository

copy and replace the accounts repository and service .AddScoped lines

