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

