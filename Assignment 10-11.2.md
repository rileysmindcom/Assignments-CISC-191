# Assignment: 10-11.2 GUI
## My Lab Objective

The lab objective is to create an application in Java using JFormattedTextField, ActionListener, and JFrame. The goal is to allow the user to enter a distance (in miles) and display multiple converted results in kilometers, meters, and feet when a button is clicked. This program helps understand user input handling, formatted text fields, and GUI layout management in Java.

## This is my Assignment 10-11.2 Code

*DistanceConverter.java*
```
package GUI;

import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.text.NumberFormat;

public class DistanceConverter extends JFrame implements ActionListener {

    private JFormattedTextField milesField;
    private JLabel kmLabel, mLabel, feetLabel;
    private JButton convertButton;

    public DistanceConverter() {
        setTitle("Distance Converter");
        setSize(400, 250);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(5, 2, 10, 10));

        JLabel milesInputLabel = new JLabel("Enter distance (miles):");
        NumberFormat numberFormat = NumberFormat.getNumberInstance();
        milesField = new JFormattedTextField(numberFormat);
        milesField.setValue(0.0);

        convertButton = new JButton("Convert");
        convertButton.addActionListener(this);

        kmLabel = new JLabel("Kilometers: ");
        mLabel = new JLabel("Meters: ");
        feetLabel = new JLabel("Feet: ");

        add(milesInputLabel);
        add(milesField);
        add(new JLabel()); 
        add(convertButton);
        add(kmLabel);
        add(new JLabel());
        add(mLabel);
        add(new JLabel());
        add(feetLabel);
        add(new JLabel());

        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        try {
            double miles = ((Number) milesField.getValue()).doubleValue();

            double kilometers = miles * 1.60934;
            double meters = miles * 1609.34;
            double feet = miles * 5280;

            kmLabel.setText(String.format("Kilometers: %.3f km", kilometers));
            mLabel.setText(String.format("Meters: %.2f m", meters));
            feetLabel.setText(String.format("Feet: %.2f ft", feet));
        } catch (Exception ex) {
            JOptionPane.showMessageDialog(this, 
                "Please enter a valid number for miles.", 
                "Input Error", 
                JOptionPane.ERROR_MESSAGE);
        }
    }

    public static void main(String[] args) {
        new DistanceConverter();
    }
}
```

## Flowchart

## Challenges Faced
My main challenge was learning how to use JFormattedTextField instead of a regular JTextField. Understanding how formatted input works with NumberFormat was confusing at first because it stores numerical values as Number objects rather than plain text. Another challenge was getting the layout organized clearly using GridLayout and aligning labels neatly on the screen.Additionally, I had to remember to handle invalid input correctly and prevent the program from crashing if the field was left blank or contained text. Using a try-catch block with JOptionPane made the interface more user-friendly by displaying error messages instead of closing the program. Overall, this lab helped me improve my understanding of formatted user input, GUI layouts, and action events in Java.
