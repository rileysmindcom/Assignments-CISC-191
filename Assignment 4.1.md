# Assignment: 4.1 Input and output
## My Lab Objective

Understand how to edit contents in a text file by reading file names from a text file, replacing parts of the string, and outputting the modified names.

## This is my Assignment 4.1 Code

PhotoInfoConverter.java
```
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class PhotoInfoConverter {
    public static void main(String[] args) {
        Scanner scnr = new Scanner(System.in);
        System.out.print("Enter file name: ");
        String fileName = scnr.nextLine();

        try {
            File inputFile = new File(fileName);
            Scanner fileScanner = new Scanner(inputFile);

            while (fileScanner.hasNextLine()) {
                String photoName = fileScanner.nextLine();
                String infoFileName = photoName.replace("_photo.jpg", "_info.txt");
                System.out.println(infoFileName);
            }

            fileScanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + fileName);
        }
    }
}
```
## My Flowchart:

## Challenges Faced:

One challenge was ensuring that the replacement only affected the _photo.jpg part of the string, without changing other parts of the file name. I also needed to remember how to properly read from a file line by line using Scanner. Another challenge was handling the case where the input file may not exist, so I added error handling with FileNotFoundException. Finally, I needed to test with an empty file to make sure no output is produced as per the requirements.

## My Assignment Video Link:

