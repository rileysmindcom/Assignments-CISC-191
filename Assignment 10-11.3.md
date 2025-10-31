# Assignment: 10-11.3 GUI

## My Lab Objective
My lab objective is to develop an application in java that transforms distance in miles to kilometers by using ActionListener, JSpinner, and JFrame. The spinner tool application allows the user to enter their distance. In a click of a button, shows how everything is converted into Kilometers. This helps with understanding how Java GUI elements play an important role in event handling layout management, and spinners to receive numerical input values to carry out calculations from someone at a distance amount to kilometers.

## Here is my Assignment 10-11.3 Code
*DistanceSpinnerConverter.java*

```
package GUI;

import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class DistanceSpinnerConverter extends JFrame implements ActionListener {

    private JSpinner milesSpinner;
    private JLabel resultLabel;
    private JButton convertButton;

    public DistanceSpinnerConverter() {
        setTitle("Distance Converter (Miles to Kilometers)");
        setSize(350, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(3, 2, 10, 10));

        JLabel milesLabel = new JLabel("Enter distance (miles):");

        SpinnerNumberModel model = new SpinnerNumberModel(0.0, 0.0, 10000.0, 0.1);
        milesSpinner = new JSpinner(model);

        convertButton = new JButton("Convert");
        convertButton.addActionListener(this);

        resultLabel = new JLabel("Result will appear here.");
        resultLabel.setForeground(Color.BLUE);

        add(milesLabel);
        add(milesSpinner);
        add(new JLabel());
        add(convertButton);
        add(new JLabel("Kilometers:"));
        add(resultLabel);

        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        try {
            double miles = (double) milesSpinner.getValue();
            double kilometers = miles * 1.60934;

            resultLabel.setText(String.format("%.3f km", kilometers));
        } catch (Exception ex) {
            JOptionPane.showMessageDialog(this,
                    "Please enter a valid number for miles.",
                    "Input Error",
                    JOptionPane.ERROR_MESSAGE);
        }
    }

    public static void main(String[] args) {
        new DistanceSpinnerConverter();
    }
}
```

## Flowchart
![Assignment 10-11 3](https://github.com/user-attachments/assets/a071fe69-f860-4691-bb7e-b9ab8b6ac528)

## Challenges Faced
Some of the things I felt challenging was observing how JSpinner works completely differently compared to using text fields. This felt challenging at first, but helped out with figuring out how to use it effectively. Second was learning how to use the SpinnerNumberModel, when learning how to set a minimum, maximum, and step values in this case helped me use appropriate range numbers to stop any invalid inputs. Third was connecting spinner values to ActionListener, which felt challenging at first, but allowed me to understand how to allow the software to read the different values of *distance (miles)* put into the program, and converting them into *Kilometers:* after the button is pressed. When I first figured out that I needed to cast the spinners values before checking twice if the value is a double multiplying everything out. The output label didn't change correctly, at the end I was able to resolve this error making sure the input values effectively outputs the input numbers as *Kilometers:*. Then was understanding how the GridLayout works to make sure everything from the labels, spinner, button, and results were all accurate and aligns with the output calculations. After fixing everything I felt this lab helped me understand how to use a JSpinner to take numbers from an input, ActionListener to handle Java GUI applications to show the results of someone or anyone between any distance of miles into Kilometers.

