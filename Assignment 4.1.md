# Assignment: 4.1 Input and output

## My Lab Objective
Describe how to edit the contents in a file by reading the names of each file from *_photo.jpg* into a text file. By replacing the parts of the string, and outputting those converted into *_info.txt*

## This is my Assignment 4.1 Code

*PhotoInfoConverter.java*
```
public class PhotoInfoConverter {
    public static void main(String[] args) {
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

        for (String photoName : photoFiles) {
            String infoFileName = photoName.replace("_photo.jpg", "_info.txt");
            System.out.println(infoFileName);
        }
    }
}
```
## My Flowchart:
![Assignment 4 1](https://github.com/user-attachments/assets/76476ded-08e3-4368-899c-ccae92ea74fb)

## Challenges Faced:

The challenges I faced were making sure that a new photo’s name ended with *_photo.jpg* so its replacement works correctly. Another was choosing whether to read the names of the file or hard-code them while maintaining the program's accuracy. Then I tested carefully to confirm each name was converted correctly into the *_info.txt* format.

## My Assignment Video Link:
https://drive.google.com/file/d/1ww-yTbAAICOWGsxaZxBpLjcu-kh2m3gP/view?usp=sharing

