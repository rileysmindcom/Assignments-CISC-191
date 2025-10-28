# Assignment: 10-11.1 GUI
## My Lab Objective

The lab objective is to create an application in Java using ActionListener, JTextField, and JFrame. That allows the user to enter their hourly rate and weekly hours worked before calculating with the results of annual salary. When two user inputs are entered into text fields. The Programs calculates the results by the click of a button. The purpose of this program is to understand how ActionListener, and user interaction works to calculating someone's Wage and Hours per week to calculate the Salary.

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
![10-11 1 GUI](https://github.com/user-attachments/assets/98c5d084-8b23-4005-8efe-55e0b03c3c23)

## Challenges Faced

My biggest challenge was figuring out how to use ActionListener correctly so that the button would work effectively that calculates the users salary. Second was making sure that the user was required to provide "*Hours per week*", and "*Hours per Wage$*", before any calculation. This prevents the program to crash when the user enters any non-numerical numbers, and was resolved at the end. I fixed this by using the handling NumberFormatException using the try-catch block using JOptionPane to display the error message. It was confusing at first to understand how to arrange the components using GridLayout, and everything felt such a learning experience understanding how to change rows, spaces, which helped create a clearer interface.

## My Assignment Video Link
https://drive.google.com/file/d/1M0QSERsgHue7Zcj8Ms2woAdZLJ218r18/view?usp=sharing
