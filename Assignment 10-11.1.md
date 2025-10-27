# Assignment: 10-11.1 GUI
## My Lab Objective

The lab objective is to design a simple Java GUI application using JFrame, JTextField, and ActionListener that allows the user to input their hourly wage and number of hours worked per week, and then calculates and displays their yearly salary. The program takes two user inputs through text fields, performs the calculation when a button is clicked, and displays the result in a label on the interface. The purpose of this assignment is to demonstrate how user interaction and event handling (using ActionListener) work in a GUI environment.

## This is my Assignment 10-11.1 Code

*SalaryCalculator.java*
```
package GUI;

import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class SalaryCalculator extends JFrame implements ActionListener {

    private JTextField hourlyWageField;
    private JTextField hoursPerWeekField;
    private JLabel resultLabel;
    private JButton calculateButton;

    public SalaryCalculator() {

        setTitle("Yearly Salary Calculator");
        setSize(400, 250);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(4, 2, 10, 10));

        JLabel wageLabel = new JLabel("Hourly Wage ($): ");
        hourlyWageField = new JTextField();

        JLabel hoursLabel = new JLabel("Hours per Week: ");
        hoursPerWeekField = new JTextField();

        calculateButton = new JButton("Calculate Yearly Salary");
        calculateButton.addActionListener(this);

        resultLabel = new JLabel("Your yearly salary will appear here.");
        resultLabel.setForeground(Color.BLUE);

        add(wageLabel);
        add(hourlyWageField);
        add(hoursLabel);
        add(hoursPerWeekField);
        add(new JLabel()); 
        add(calculateButton);
        add(new JLabel("Result:"));
        add(resultLabel);

        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        try {
            double hourlyWage = Double.parseDouble(hourlyWageField.getText());
            double hoursPerWeek = Double.parseDouble(hoursPerWeekField.getText());

            double yearlySalary = hourlyWage * hoursPerWeek * 52;
            resultLabel.setText(String.format("$%.2f per year", yearlySalary));
        } catch (NumberFormatException ex) {
            JOptionPane.showMessageDialog(this, 
                "Please enter valid numbers for both fields.", 
                "Input Error", 
                JOptionPane.ERROR_MESSAGE);
        }
    }

    public static void main(String[] args) {
        new SalaryCalculator();
    }
}
```
## My Flowchart:

## Challenges Faced

The main challenge I faced was understanding how to properly use ActionListener to make the button respond to user clicks. I had to ensure that the calculation only happened after the user entered both inputs. Another challenge was preventing the program from crashing when users entered non-numeric values. I solved this by using a try-catch block to handle NumberFormatException and display an error message using JOptionPane. Learning how to organize the components using a GridLayout was slightly confusing at first, but it helped create a cleaner interface once I adjusted the rows and spacing.

## My Assignment Video Link
