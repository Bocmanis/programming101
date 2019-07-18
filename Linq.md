https://docs.microsoft.com/en-us/dotnet/api/system.linq.enumerable.aggregate?view=netframework-4.8
## .Where()
```c#
List<string> fruits = new List<string> { "apple", "passionfruit", "banana", "mango", 
                    "orange", "blueberry", "grape", "strawberry" };

IEnumerable<string> query = fruits.Where(fruit => fruit.Length < 6);

foreach (string fruit in query)
{
    Console.WriteLine(fruit);
}
/*
 This code produces the following output:

 apple
 mango
 grape
*/
```

## .Distinct()
```c#
List<int> ages = new List<int> { 21, 46, 46, 55, 17, 21, 55, 55 };

IEnumerable<int> distinctAges = ages.Distinct();

Console.WriteLine("Distinct ages:");

foreach (int age in distinctAges)
{
    Console.WriteLine(age);
}

/*
 This code produces the following output:

 Distinct ages:
 21
 46
 55
 17
*/
```
## First() & FirstOrDefault()
First() return the first element or throws error if none is found.
FirstOrDefault() does the same, but instead of throwing it returns null

```c#
string[] names = { "Hartono, Tommy", "Adams, Terry", 
                     "Andersen, Henriette Thaulow", 
                     "Hedlund, Magnus", "Ito, Shu" };

string firstLongName = names.FirstOrDefault(name => name.Length > 20);

Console.WriteLine("The first long name is '{0}'.", firstLongName);

string firstVeryLongName = names.FirstOrDefault(name => name.Length > 30);

Console.WriteLine(
    "There is {0} name longer than 30 characters.",
    string.IsNullOrEmpty(firstVeryLongName) ? "not a" : "a");

/*
 This code produces the following output:

 The first long name is 'Andersen, Henriette Thaulow'.
 There is not a name longer than 30 characters.
*/
```
## Max()
```c#
double?[] doubles = { null, 1.5E+104, 9E+103, -2E+103 };

double? max = doubles.Max();

Console.WriteLine("The largest number is {0}.", max);

/*
 This code produces the following output:

 The largest number is 1.5E+104.
*/
```
## Any() & All()
```c#
class Pet
{
    public string Name { get; set; }
    public int Age { get; set; }
}
class Person
{
    public string LastName { get; set; }
    public Pet[] Pets { get; set; }
}

public static void AnyEx2()
{
    List<Person> people = new List<Person>
        { new Person { LastName = "Haas",
                       Pets = new Pet[] { new Pet { Name="Barley", Age=10 },
                                          new Pet { Name="Boots", Age=14 },
                                          new Pet { Name="Whiskers", Age=6 }}},
          new Person { LastName = "Fakhouri",
                       Pets = new Pet[] { new Pet { Name = "Snowball", Age = 1}}},
          new Person { LastName = "Antebi",
                       Pets = new Pet[] { }},
          new Person { LastName = "Philips",
                       Pets = new Pet[] { new Pet { Name = "Sweetie", Age = 2},
                                          new Pet { Name = "Rover", Age = 13}} }
        };

    // Determine which people have a non-empty Pet array.
    IEnumerable<string> names = from person in people
                                where person.Pets.Any()
                                select person.LastName;

    foreach (string name in names)
    {
        Console.WriteLine(name);
    }

    /* This code produces the following output:
      
       Haas
       Fakhouri
       Philips
    */
}
```
## Select()

```c#
string[] fruits = { "apple", "banana", "mango", "orange", 
                      "passionfruit", "grape" };

var query =
    fruits.Select((fruit, index) =>
                      new { index, str = fruit.Substring(0, index) });

foreach (var obj in query)
{
    Console.WriteLine("{0}", obj);
}

/*
 This code produces the following output:

 {index=0, str=}
 {index=1, str=b}
 {index=2, str=ma}
 {index=3, str=ora}
 {index=4, str=pass}
 {index=5, str=grape}
*/
```
