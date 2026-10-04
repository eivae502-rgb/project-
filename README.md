using System;
using System.Collections.Generic;

class person
{
    public string Name;
    public person(string name)
    {
        Name = name;
    }
    public virtual void DisplayInfo()
    {
        Console.WriteLine("Name:" + Name);
    }
}
class Student : person
{
    public int StudentID;
    public Student(string name, int studentID):base(name)
    {
        StudentID = studentID;
    }
    public override void DisplayInfo()
    {
        Console.WriteLine("Student Name:" + Name);
        Console.WriteLine("StudentID :" + StudentID);
    }
}
class Employee : person
{
    public double Salary;
    public Employee(string name,double salary):base(name)
    {
        Salary = salary;
    }
    public override void DisplayInfo()
    {
        Console.WriteLine("Employee Name:" + Name);
        Console.WriteLine("Salary :" + Salary);
    }
}
class Teacher : person
{
    public string CourseName;
    public Teacher(string name, string courseName):base(name)
    {
        CourseName = courseName;
    }
    public override void DisplayInfo()
    {
        Console.WriteLine("Teacher Name:"+ Name);
        Console.WriteLine("Course:"+ CourseName);
    }
}
class program
{
    static void ShowPerson(person person)
    {
        person. DisplayInfo();
    }
    static void Main()
    {
        List<person> people = new List<person>();
        people.Add(new Student("Sara", 101));
        people.Add(new Employee("Ahmed", 5000));
        people.Add(new Teacher("Mohamed", "c# Programming"));
        foreach(person person in people)
        {
            Console.WriteLine("Runtime:" + person.GetType().Name);
            person.DisplayInfo();
            Console.WriteLine();
        }
        ShowPerson(people[0]);
    }
}
OUTPUT:
Runtime:Student
Student Name:Sara
StudentID :101
Runtime:Employee
Employee Name:Ahmed
Salary :5000
Runtime:Teacher
Teacher Name:Mohamed
Course:c# Programming
Student Name:Sara
StudentID :101
# project-