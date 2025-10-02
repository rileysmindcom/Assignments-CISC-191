# Assignment: 5-6.2 Derived Classes

## My Lab Objective

The objective of this lab is to explain how derived classes can inherit data, and methods from a base class. General Course data involves with a course number, and title all stored into lab Course class. By combining details with the instructor name, location, class time, and the derived class called *OfferedCourse* to expand that course. To keep everything assigned, and print data to the application creating objects to both Course, and OfferedCourse.

## This is my Assignment 5-6.2 Code

*Course.java*
```
public class Course {
    private String courseNumber;
    private String courseTitle;

    public void setCourseNumber(String number) {
        courseNumber = number;
    }

    public void setCourseTitle(String title) {
        courseTitle = title;
    }

    public String getCourseNumber() {
        return courseNumber;
    }

    public String getCourseTitle() {
        return courseTitle;
    }

    public void printInfo() {
        System.out.println("Course Information:");
        System.out.println("   Course Number: " + courseNumber);
        System.out.println("   Course Title: " + courseTitle);
    }
}
```

*OfferedCourse.java*
```
public class OfferedCourse extends Course {
    private String instructorName;
    private String location;
    private String classTime;

    public void setInstructorName(String name) {
        instructorName = name;
    }

    public void setLocation(String loc) {
        location = loc;
    }

    public void setClassTime(String time) {
        classTime = time;
    }

    public String getInstructorName() {
        return instructorName;
    }

    public String getLocation() {
        return location;
    }

    public String getClassTime() {
        return classTime;
    }

    @Override
    public void printInfo() {
        super.printInfo();
        System.out.println("   Instructor Name: " + instructorName);
        System.out.println("   Location: " + location);
        System.out.println("   Class Time: " + classTime);
    }
}
```

*CourseDemo.java*
```
public class CourseDemo {
    public static void main(String[] args) {

        Course course1 = new Course();
        course1.setCourseNumber("CS101");
        course1.setCourseTitle("Introduction to Programming");
        course1.printInfo();

        System.out.println();

        OfferedCourse course2 = new OfferedCourse();
        course2.setCourseNumber("CS202");
        course2.setCourseTitle("Data Structures");
        course2.setInstructorName("Ralph Anderson");
        course2.setLocation("Room 101");
        course2.setClassTime("MWF: 10-11:30 am");
        course2.printInfo();
    }
}

```

## My Flowchart
<img width="1063" height="515" alt="Activity 5-6 2 Inheritance" src="https://github.com/user-attachments/assets/ac4deaf6-a92c-441a-8969-b419e3507bb8" />

## Challenges Faced

The challenges were making sure OfferedCourse was able to add its own fields while properly drawing on Course's methods. When packaging, I had to keep in mind of employing private fields with the getter, and setter methods. Another was using super.printInfo() to replace printInfo() without taking a risk of erasing the original output from Course necessarily. Then ensuring everything had appropriate spacing that would fit the consoles output, that would match a similar desired output related to *Derived Classes*

## My Assignment Video Link
