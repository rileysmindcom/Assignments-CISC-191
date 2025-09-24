# Assignment: 4.1 Input and output

## My Lab Objective
The objective of this lab is to read photo filenames starting with a text file called *ParkPhotos.txt*, as each filename must contain only letters, and numbers stored on every separate line. Then the program replaces *_photo.jpg* converting the filename to *_info.txt*. If the text file is empty, the program produces no output.

## This is my Assignment 4.1 Code

*PhotoInfoConverter.java*
```
package ParkPhotos;

import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class PhotoInfoConverter {
    public static void main(String[] args) {
        String inputFileName = "ParkPhotos.txt";

        try {
            File inputFile = new File(inputFileName);
            Scanner scanner = new Scanner(inputFile);

            while (scanner.hasNextLine()) {
                String photoName = scanner.nextLine().trim();
                if (!photoName.isEmpty()) {
                    String infoFileName = photoName.replace("_photo.jpg", "_info.txt");
                    System.out.println(infoFileName);
                }
            }

            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error: Could not find file -> " + inputFileName);
        }
    }
}
```

*ParkPhotos.txt*
```Yellowstone2015_photo.jpg
Everglades1999_photo.jpg
GlacierBay2001_photo.jpg
MesaVerde2018_photo.jpg
Olympic1994_photo.jpg
Shenandoah2007_photo.jpg
Denali2012_photo.jpg
Sequoia1988_photo.jpg
BryceCanyon2010_photo.jpg
Zion2005_photo.jpg
GreatSmokyMountains2003_photo.jpg
RockyMountain1997_photo.jpg
```

## My Flowchart:
![Assignment 4 1](https://github.com/user-attachments/assets/76476ded-08e3-4368-899c-ccae92ea74fb)

## Challenges Faced:

The challenges I faced in this lab were making sure each photo filename ended with *_photo.jpg* so the replacement would end effectively. Deciding whether to hard-code the filenames or read them from a text file, then carefully placing ParkPhotos.txt outside of the src folder so the program can find and read each file fully converting them into *_into.txt*.

## My Assignment Video Link:
https://drive.google.com/file/d/1UyPwqMUM9Up_gJfmDsOKc66nP8StjBY8/view?usp=drive_link

