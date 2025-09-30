# Assignment: 5-6.1 Inheritance
## My Lab Objective
The goal of this lab is to reveal how sub-classes can obtain methods, and data from the parent class. While student classes extend person by adding a unique ID, the person class defines important properties such as name, and age. The application uses a method called sub-classes which constructs student object to assign values, and print them.

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
