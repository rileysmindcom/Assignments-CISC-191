# Assignment: 10-11.2 GUI
## My Lab Objective

The lab objective goal is to use JFormattedTextField, ActionListener, and JFrame to develop an application in Java. The process is the user inputs their distance into miles through the click of a button, which shows how many converted values are in kilograms, feet, and meters. The purpose of this program is to understand how Jave text fields, Gui layout managements, and user inputs play an important role into calculating the users distance in miles to getting the results of Kilometers, Meters, and Feet.

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
![Assignment 10-11 2](https://github.com/user-attachments/assets/da65e580-a816-4b28-964c-da2cfadf2c16)

## Challenges Faced
Some of the challenges were learning how to use the JFormmatedTextField instead of the JText Field because the NUmberformat maintains numerical data just as Number objects as plain text, which made sense when I was able to learn how to use a formatted input for NumberFormat. Second was using the Grid Layout to structure everything with the layout with position labels accurately, which was difficult at first, and easily understandable structuring everything out. Third was figuring out how to properly handle invalid inputs to keep the software from crashing if any fields were left empty including text. Fourth was using the try-catch block with the JOptionPane, which displayed error messages at first instead of shutting down the application, which was resolved. At last everything else has taught me how to understand Java action events, structured user inputs, and GUI layouts.

## My Assignment Video Link
https://drive.google.com/file/d/1jpe23HYAivotmA1p8EZe5yLLA7-hKz8E/view?usp=sharing
