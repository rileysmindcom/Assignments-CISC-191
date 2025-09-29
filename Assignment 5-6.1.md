# Assignment: 5-6.1 Inheritance
## My Lab Objective

The objective of this lab is to demonstrate how subclasses can inherit data and methods from a superclass. The Person class defines common attributes such as name and age, while the Student class extends Person by adding a unique ID. The program creates a Student object, assigns values, and prints them using both inherited and subclass methods.

## This is my Assignment 5-6.1 Code
Person.java
```
public class Person {
   private int ageYears;
   private String lastName;

   public void setName(String userName) {
      lastName  = userName;
   }

   public void setAge(int numYears) {
      ageYears = numYears;
   }

   public void printAll() {
      System.out.print("Name: " + lastName);
      System.out.print(", Age: "  + ageYears);
   }
}
```
Student.java
```
public class Student extends Person {
   private int idNum;

   public void setID(int studentId) {
      idNum = studentId;
   }

   public int getID() {
      return idNum;
   }
}
```
StudentDerivationFromPerson.java
```
public class StudentDerivationFromPerson {
   public static void main(String[] args) {
      Student courseStudent = new Student();

      courseStudent.setName("Arnold");
      courseStudent.setAge(20);
      courseStudent.setID(9999);

      courseStudent.printAll();
      System.out.println(", ID: " + courseStudent.getID());
   }
}
```

## My Flowchart


## Challenges Faced

The challenges I faced in this lab were: Making sure that the Student class correctly inherited methods from the Person class. Remembering that idNum is private in Student, so it needed getter and setter methods. Handling the output correctly since printAll() doesn’t end with a newline, so I needed a separate println() for the ID.

## My Assignment Video Link
