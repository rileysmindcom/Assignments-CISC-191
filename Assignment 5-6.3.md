# Assignment: 5-6.3: Overriding methods
## My Lab Objective


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

    public void setEdition(String edition) {
        this.edition = edition;
    }

    public void setNumPages(int pages) {
        this.numPages = pages;
    }

    public String getEdition() {
        return edition;
    }

    public int getNumPages() {
        return numPages;
    }

    @Override
    public void printInfo() {
        System.out.println("--- Encyclopedia Record ---");
        System.out.println("   Title: " + getTitle());
        System.out.println("   Written by: " + getAuthor());
        System.out.println("   Published by: " + getPublisher());
        System.out.println("   Date of Publication: " + getPublicationDate());
        System.out.println("   Edition: " + edition);
        System.out.println("   Total Pages: " + numPages);
    }
}
```

BookDemo.java

```
import java.util.Scanner;

public class BookDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String title1 = sc.nextLine().split("Title: ")[1];
        String author1 = sc.nextLine().split("Written by: ")[1];
        String publisher1 = sc.nextLine().split("Published by: ")[1];
        String pubDate1 = sc.nextLine().split("Date of Publication: ")[1];

        Book book1 = new Book();
        book1.setTitle(title1);
        book1.setAuthor(author1);
        book1.setPublisher(publisher1);
        book1.setPublicationDate(pubDate1);
        
        String title2 = sc.nextLine().split("Title: ")[1];
        String author2 = sc.nextLine().split("Written by: ")[1];
        String publisher2 = sc.nextLine().split("Published by: ")[1];
        String pubDate2 = sc.nextLine().split("Date of Publication: ")[1];
        String edition = sc.nextLine().split("Edition: ")[1];
        int pages = Integer.parseInt(sc.nextLine().split("Total Pages: ")[1]);

        Encyclopedia encyclopedia1 = new Encyclopedia();
        encyclopedia1.setTitle(title2);
        encyclopedia1.setAuthor(author2);
        encyclopedia1.setPublisher(publisher2);
        encyclopedia1.setPublicationDate(pubDate2);
        encyclopedia1.setEdition(edition);
        encyclopedia1.setNumPages(pages);

        book1.printInfo();
        System.out.println();
        encyclopedia1.printInfo();
    }
}
```
## My Flowchart:

## Challenges Faced:
