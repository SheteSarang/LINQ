# LINQ

using System;
using System.Collections.Generic;
using System.Linq;
 
class Employee
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}
 
class Program
{
    static void Main(string[] args)
    {
        // Sample list of employees
        var employees = new List<Employee>
        {
            new Employee { Id = 1, Name = "John", Age = 30 },
            new Employee { Id = 2, Name = "Sara", Age = 25 },
            new Employee { Id = 3, Name = "Mark", Age = 35 },
            new Employee { Id = 4, Name = "Lucy", Age = 28 },
            new Employee { Id = 5, Name = "Ana", Age = 24 }
        };
 
        // LINQ query to filter and order employees
        var filteredEmployees = employees
            .Where(emp1 => emp1.Name.Length ==4 )       // Filter by name length
            .OrderBy(emp1 => emp1.Age)                 // Order by age
            .Select(emp1=> new { emp1.Name, emp1.Age }) // Extract Name and Age
            .ToList();
 
        // Print the filtered employees
        foreach (var emp1 in filteredEmployees)
        {
            Console.WriteLine($"Name: {emp1.Name}, Age: {emp1.Age}");
        }
    }
  }
