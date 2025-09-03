# Assignment: 1.2 Salary and Tax Calculation

## My Lab Objective

Recall by using setters, a Java class, and constructor overloading to solve the tax rate, and calculate the tax to pay for the given annual salary.

This is my Assignment 1.2 Code
TaxTableTools.java
```
public class TaxTableTools {
    private int[] salaryTable;
    private double[] taxRateTable;
    private int nEntries;

    public TaxTableTools() {
        this.salaryTable = new int[]{0, 50000, 100000};
        this.taxRateTable = new double[]{0.10, 0.20, 0.30};
        this.nEntries = salaryTable.length;
    }

    public TaxTableTools(int[] salaries, double[] rates) {
        if (salaries.length == rates.length) {
            this.salaryTable = salaries;
            this.taxRateTable = rates;
            this.nEntries = salaries.length;
        } else {
            throw new IllegalArgumentException("Salary and Tax Rate tables must be same length.");
        }
    }

    public void setTaxTables(int[] salaries, double[] rates) {
        if (salaries.length == rates.length) {
            this.salaryTable = salaries;
            this.taxRateTable = rates;
            this.nEntries = salaries.length;
        } else {
            System.out.println("Error: Salary and Tax Rate tables must be the same length.");
        }
    }

    public double getTaxRate(int salary) {
        for (int i = nEntries - 1; i >= 0; i--) {
            if (salary >= salaryTable[i]) {
                return taxRateTable[i];
            }
        }
        return 0.0;
    }
}
```
IncomeTaxMain.java
```import java.util.Scanner;

public class IncomeTaxMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int[] salaryTable = {0, 40000, 70000, 100000};
        double[] rateTable = {0.08, 0.18, 0.28, 0.38};

        TaxTableTools tools = new TaxTableTools(salaryTable, rateTable);

        while (true) {
            System.out.print("Enter annual salary (-1 to quit): ");
            int salary = sc.nextInt();
            if (salary == -1) break;

            double rate = tools.getTaxRate(salary);
            double tax = salary * rate;

            System.out.printf("Salary: %d, Tax Rate: %.2f, Tax to Pay: %.2f%n", 
                              salary, rate, tax);
        }

        sc.close();
    }
}
```
## My Flowchart
![2 1 Assignment_ 1 2 Salary and Tax Calculation](https://github.com/user-attachments/assets/622ef244-28f1-4426-afa0-b7403eadc3cb)

## Challenges Faced
First I had to ensure the main program was linked to the TaxTableTools class because the tax tables took extra time to review. Then I solved it by adding a method that constructed the overload. I ran into some bugs where salary and rate tables experienced different lengths. Which may have gotten me error messages on the first tries, until I figured out the issue. My third challenge on my third attempt was remembering how many times to test multiple salaries, such as 10000, 50000, 50001, 100001, and -1, making sure those ranges were correct. 

## My Assignment Video
