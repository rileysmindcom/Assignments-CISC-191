# Assignment: 3.1 Memory Management Using Classes

## My Lab Objective
Recall by describing how memory management operates in Java through creating objects, observing stacks versus heap memory allocation, and explaining what the Garbage Collector does. And, how does it work?

## This is my Assignment 3.1 Code

MemoryManagementDemo.java

```
public class MemoryManagementDemo {
    private String taskName;
    private int duration;

    public MemoryManagementDemo(String taskName, int duration) {
        this.taskName = taskName;
        this.duration = duration;
        System.out.println("Task object created: " + taskName);
    }

    public void displayTask() {
        System.out.println("Task: " + taskName + ", Duration: " + duration + " hours");
    }

    public static void main(String[] args) {

        MemoryManagementDemo task1 = new MemoryManagementDemo("Study Java", 3);
        MemoryManagementDemo task2 = new MemoryManagementDemo("Exercise", 1);

        task1.displayTask();
        task2.displayTask();

        task1 = null;

        System.gc();

        System.out.println("End of main method.");
    }
}
```

## My Flowchart
![3 1 Memory Management Using Classes](https://github.com/user-attachments/assets/81e0f311-a7d5-42e3-982f-df1607eb4028)


## Challenges Faced

The challenges I stumbled upon were: learning how to differentiate stack versus heap memory during object creation. Second, it was to understand how garbage collection behaves, because Java doesn’t always guarantee immediate memory freeing. Testing for nullification at *task1 = null*. This is because I had to go back and observe every effect without causing any exceptions. My last challenge was creating a clear example that demonstrates how memory management works, while making sure everything made sense when testing memory management using classes.

## My Assignment Video
