# Assignment: 5-6.3: Overriding methods
## My Lab Objective
The main goal of this lab is to create a base class called *Book*, and a derived class such as Encyclopedia to practice method overriding. The Encyclopedia class takes information from the book, and adds its own fields in addition to count pages for the book storing title, publisher author, and release date. The importance of this experiment is to explain how derived classes can expand the abilities out of a base class by customizing the printInfo() method.

## This is my Assignment Code

*Book.java*

```
public class Book {
    private String title;
    private String author;
    private String publisher;
    private String publicationDate;

    public void setTitle(String title) {
        this.title = title;
    }
    public void setAuthor(String author) {
        this.author = author;
    }
    public void setPublisher(String publisher) {
        this.publisher = publisher;
    }
    public void setPublicationDate(String date) {
        this.publicationDate = date;
    }

    public String getTitle() {
        return title;
    }
    public String getAuthor() {
        return author;
    }
    public String getPublisher() {
        return publisher;
    }
    public String getPublicationDate() {
        return publicationDate;
    }

    public void printInfo() {
        System.out.println("--- Book Record ---");
        System.out.println("   Title: " + title);
        System.out.println("   Written by: " + author);
        System.out.println("   Published by: " + publisher);
        System.out.println("   Date of Publication: " + publicationDate);
    }
}
```

*Encyclopedia.java*

```
public class Encyclopedia extends Book {
    private String edition;
    private int numPages;

    public void setEdition(String edition) { this.edition = edition; }
    public void setNumPages(int pages) { this.numPages = pages; }
    public String getEdition() { return edition; }
    public int getNumPages() { return numPages; }

    @Override
    public void printInfo() {

        super.printInfo();

        System.out.println("Edition: " + edition);
        System.out.println("Total Pages: " + numPages);
    }
}

```

BookDemo.java

```
public class BookDemo {
    public static void main(String[] args) {
        
        Encyclopedia encyclopedia = new Encyclopedia();
        encyclopedia.setTitle("The Illustrated Encyclopedia of the Universe");
        encyclopedia.setAuthor("Ian Ridpath");
        encyclopedia.setPublisher("Watson-Guptill");
        encyclopedia.setPublicationDate("2001");
        encyclopedia.setEdition("2nd");
        encyclopedia.setNumPages(384);

        encyclopedia.printInfo();
    }
}

```
## My Flowchart:
<img width="1165" height="609" alt="Activity 5-6 3 Overriding" src="https://github.com/user-attachments/assets/5a5e54ff-a8a7-40fd-bbfe-d643444e71a9" />

## Challenges Faced:
My first challenge was to make sure that Encyclopedia was modified printInfo() as a method to the book information without duplicating any written code. I solved this by adding Encyclopedia information after reusing the parent class as an output with super.printInfo(). Then carefully controlling the input order to make sure the scanner works correctly that reads the string, and int data presented.

# Assignment Video
