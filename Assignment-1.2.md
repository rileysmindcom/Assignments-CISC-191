
# Assignment: 1.2 Word Frequencies

## My Lab Objective
Recall by counting the number of times a word appears between any array of words. The method for the assignment is:

``` public static int getWordFrequency(String[] wordsList, int listSize, String currWord) ```

This allows for how many times currWord appears within the list of words

# This is my Assignment 1.2 Code
```
public class Main {

    public static int getWordFrequency(String[] wordsList, int listSize, String currWord) {
        int count = 0;
        for (int i = 0; i < listSize; i++) {
            if (wordsList[i].equalsIgnoreCase(currWord)) {
                count++;
            }
        }
        return count;
    }

    public static void main(String[] args) {

        String input = "Cat bird cat Bird CAT bird";

        String[] wordsList = input.split(" ");
        int listSize = wordsList.length;

        for (int i = 0; i < listSize; i++) {
            String currWord = wordsList[i];
            int freq = getWordFrequency(wordsList, listSize, currWord);
            System.out.println(currWord + " " + freq);
        }
    }
}
```
## My Example Input / Output

Input:

``` Cat bird cat Bird CAT bird ```


Output:

``` Cat 3
bird 3
cat 3
Bird 3
CAT 3
bird 3
```

## Flowchart


## Frequency Analysis of a Website

If I had to develop a frequency analysis website. I would extract the website by using web scraping, copy and paste by removing any punctuations to convert every word to lowercase, by split the text into individual words. Allowing the count method that counts occurrences, which would generate a report of words by analyzing what is most common.

## Challenges Faced

Some of the challenges were comparing making a case-insensitive so that words like cat, Cat, and CAT counted the same by using equalsIgnoreCase(). Using Loop correctness, which makes sure the loop travels from every word in the array that counts to these occurrences. And then, understanding the repeated output of the program by looking at every word multiple times as an output.

# Assignment Video
