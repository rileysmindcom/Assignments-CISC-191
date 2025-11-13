# Assignment: Insertion Sort Lab 12.1

## Lab Objective
My lab objective is to write a program in java that executes an insertion sort on an integer array to understand how sequential workings connects with sorting algorithms. This software executes the insertion sort to print each intermediate state of the array to read the array's size, and its elements producing the original array, and then showing the total number of comparisons with swaps created by the sorting process. At last is using the output formatting to convert the sorting theory.

## My 12.1 Assignment Code: 
*InsertionSort.java*
```
import java.util.Scanner;

public class InsertionSort {
   public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);

      int size = sc.nextInt();
      int[] arr = new int[size];

      for (int i = 0; i < size; i++) {
         arr[i] = sc.nextInt();
      }

      printArray(arr);

      int comparisons = 0;
      int swaps = 0;

      for (int i = 1; i < size; i++) {
         int key = arr[i];
         int j = i - 1;

         while (j >= 0) {
            comparisons++;

            if (arr[j] > key) {
               arr[j + 1] = arr[j];
               swaps++;
               j--;
            } else {
               break;
            }
         }

         arr[j + 1] = key;

      }

      System.out.println();
      System.out.println("comparisons: " + comparisons);
      System.out.println("swaps: " + swaps);
   }

   public static void printArray(int[] arr) {
      for (int x : arr) {
         System.out.print(x + " ");
      }
      System.out.println();
   }
}
```

## Flowchart:


## Challenges Faced:
The first challenge I've encountered this lab was understanding how to design the algorithm and execution. This was because it took time to explore how the insertion sort works to tracking these activities with the shifting process, another was making sure the comparisons and swaps were counted properly to make sure that the order process matched the output format. Third was I had to make sure that the array was printed correctly for each cycle. Fourth was seeing how the items changed during insertion sort. This has helped me a ton to make these connections with the flowchart representing this method. At last was carefully testing to make sure the code was operating correctly when it came to handling the input format, which involves reading size before processing each item. This made everything much easier with the internal workings of insertion sort making things much clear to understand.

