# Assignment: 1.1 Sorting an Array

## My Lab Objective
Sort an array in **descending order**.

Recall `sortArray(int[] myArr, int arrSize)` in Java.


## This is my Assignment 1.1 Code

```java
public class Main {
    public static void sortArray(int[] myArr, int arrSize) {
        for (int i = 0; i < arrSize - 1; i++) {
            for (int j = 0; j < arrSize - i - 1; j++) {
                if (myArr[j] < myArr[j + 1]) { 
                    int temp = myArr[j];
                    myArr[j] = myArr[j + 1];
                    myArr[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        
        int[] myArr = {8, 3, 15, 1, 22, 7};
        int arrSize = myArr.length;

        sortArray(myArr, arrSize);

        for (int i = 0; i < arrSize; i++) {
            if (i > 0) System.out.print(",");
            System.out.print(myArr[i]);
        }
        System.out.println();
    }
}
```


# My Re-Written Example

Input: 6 8 3 15 1 22 7

Output: 22, 15, 8, 7, 3, 1 


# This is my Flowchart

![Assignment_ Flowchart Sorting an Array](https://github.com/user-attachments/assets/c11e6c0e-f018-4ea9-945f-aaa3b66815aa)


# Why did I select this specific sorting algorithm?
I saw the bubble sort algorithm as an easy method to implement for small arrays. Because the assignment has fewer than 20 elements, this allowed me to sort out the arrays in descending order.

# Challenges Faced
The challenges I faced were sorting things in descending order rather than ascending order. I saw that it was important to adjust the conditions by using comparison so the large numbers would come first.

