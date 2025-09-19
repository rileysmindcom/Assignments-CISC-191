# Assignment: 4.1 Input and output
## My Lab Objective

Understand how to edit contents in a text file by reading file names from a text file, replacing parts of the string, and outputting the modified names.

## This is my Assignment 4.1 Code

PhotoInfoConverter.java
```
public class PhotoInfoConverter {
    public static void main(String[] args) {
        // New list of photo file names
        String[] photoFiles = {
            "Yellowstone2015_photo.jpg",
            "Everglades1999_photo.jpg",
            "GlacierBay2001_photo.jpg",
            "MesaVerde2018_photo.jpg",
            "Olympic1994_photo.jpg",
            "Shenandoah2007_photo.jpg",
            "Denali2012_photo.jpg",
            "Sequoia1988_photo.jpg",
            "BryceCanyon2010_photo.jpg",
            "Zion2005_photo.jpg",
            "GreatSmokyMountains2003_photo.jpg",
            "RockyMountain1997_photo.jpg"
        };

        // Loop through each file and replace _photo.jpg with _info.txt
        for (String photoName : photoFiles) {
            String infoFileName = photoName.replace("_photo.jpg", "_info.txt");
            System.out.println(infoFileName);
        }
    }
}
```
## My Flowchart:

## Challenges Faced:

One challenge was ensuring that the replacement only affected the _photo.jpg part of the string, without changing other parts of the file name. I also needed to remember how to properly read from a file line by line using Scanner. Another challenge was handling the case where the input file may not exist, so I added error handling with FileNotFoundException. Finally, I needed to test with an empty file to make sure no output is produced as per the requirements.

## My Assignment Video Link:

