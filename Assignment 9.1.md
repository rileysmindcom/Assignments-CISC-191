# Assignment: 9.1 Collections

## My Lab Objective

The lab objective is to use a java deque to reveal if a string given is a palindrome. A palindrome string is a civic or level, which reads both forward and backward. The purpose of this application is to examine a line text, which the user has entered eliminates any punctuation or spaces to represent if the character sequence is the same or in reverse. Third is to determine whether the input is a palindrome should be made evident in the output with a workable string of one character as a palindrome.

## This is my Assignment 5.1 Code

*PalindromeChecker.java*

```
package Collections;

import java.util.Deque;
import java.util.LinkedList;
import java.util.Scanner;

public class PalindromeChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter text: ");
        String input = scanner.nextLine().toLowerCase().replaceAll("[^a-z]", "");

        Deque<Character> deque = new LinkedList<>();

        for (char c : input.toCharArray()) {
            deque.add(c);
        }

        boolean isPalindrome = true;

        while (deque.size() > 1) {
            if (deque.removeFirst() != deque.removeLast()) {
                isPalindrome = false;
                break;
            }
        }

        if (isPalindrome) {
            System.out.println("Yes, " + input + " is a palindrome.");
        } else {
            System.out.println("No, \"" + input + "\" is not a palindrome.");
        }

        scanner.close();
    }
}
```


## My Flowchart:
<img width="808" height="755" alt="9 1 collections" src="https://github.com/user-attachments/assets/a6726e2c-3004-4983-ad99-f691c96faf78" />

## Challenges Faced:

The first challenge I faced was correctly using a Deque to remove and compare the characters the end of the string during this lab experiment. Second was to see a comparison by eliminating all punctuation and spaces to convert letters into lowercase. At last was making sure that the program could solve edge circumstances from single character strings into empty input lines correctly into error-free, which helped a ton with this process.

## My Assignment Video Link:
https://drive.google.com/file/d/1Zg-e6_X3kCVhqSwcmvZvnyJrBKRoTVtO/view?usp=drive_link
