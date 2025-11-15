# Assignment: Merge Sort Lab 12.2
## Lab Objective
The objective of this lab is to understand how the recursive divide algorithms operate by writing a program in java that does merge sort on an integer array. After determining the size of the array the program reads the array's items, output the unsorted array, and perform a merge sort to keep track of how many comparisons were created. The sorted array, and total number of comparisons are used during the merge operation as an output to the console.

## My 12.2 Assignment Code:

*MergeSort.java*
```
import java.util.Scanner;

public class MergeSort {

    static int comparisons = 0;

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int size = sc.nextInt();
        int[] arr = new int[size];

        for (int i = 0; i < size; i++) {
            arr[i] = sc.nextInt();
        }

        System.out.print("unsorted: ");
        printArray(arr);

        mergeSort(arr, 0, arr.length - 1);

        System.out.print("\nsorted:   ");
        printArray(arr);

        System.out.println("\ncomparisons: " + comparisons);
    }

    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = (left + right) / 2;

            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            merge(arr, left, mid, right);
        }
    }

    public static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] L = new int[n1];
        int[] R = new int[n2];

        for (int i = 0; i < n1; i++) {
            L[i] = arr[left + i];
        }
        for (int j = 0; j < n2; j++) {
            R[j] = arr[mid + 1 + j];
        }

        int i = 0, j = 0;
        int k = left;

        while (i < n1 && j < n2) {
            comparisons++;
            if (L[i] <= R[j]) {
                arr[k++] = L[i++];
            } else {
                arr[k++] = R[j++];
            }
        }

        while (i < n1) {
            arr[k++] = L[i++];
        }

        while (j < n2) {
            arr[k++] = R[j++];
        }
    }

    public static void printArray(int[] arr) {
        for (int x : arr) {
            System.out.print(x + " ");
        }
    }
}
```

## Flowchart:
![12 2 Diagram](https://github.com/user-attachments/assets/6fcb0108-f3be-4c20-bc87-b88db42e89ad)

## Challenges Faced:

The first challenge I've struggled was using the recursive to division to the array into smaller portions, which helped me a lot to understand what went wrong. Second was keeping track of the left, right, and mid points carefully through the design because the merge sort is a divide algorithm. Since this is the main area where comparisons take place, makes it easier to execute any procedures. Every merge I had to make sure the comparisons counter rose was appropriately presented in the operations. Another difficulty was organizing the left and right arrays when merging all remaining elements were copied after the main loop was presented. In order to ensure that the output was format correctly. At last was testing my code using the sample format to consider everything worked out well. Which, helped me improve my understanding between the recursive and merge sort algorithms while using insertion sort.
