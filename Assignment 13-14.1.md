# Assignment: Manipulating Databases Using Java 13-14.1
## My Lab Objective
My goal of this lab is to understand how java can use MySQL J Connector to connect with a database by adding, and updating existing records. This lab uses the Miramar database and student table. To explore how SQL statements run, and work inside of Java by inserting student information as the teacher example, "Philip David Charles Collins", to modify his current zip code.

## My Assignment 13-14.1 Code
*DatabaseConnection.java*
```
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class DatabaseConnection {
    public static void main(String[] args) {

        String url = "jdbc:mysql://localhost:3306/Miramar";
        String username = "root";
        String password = "MyLab7865";

        try {

            Connection conn = DriverManager.getConnection(url, username, password);
            System.out.println("Connected to the database successfully!");

            String deleteSQL = "DELETE FROM Student WHERE SSN = ?";
            PreparedStatement deleteStmt = conn.prepareStatement(deleteSQL);
            deleteStmt.setString(1, "111222333");
            deleteStmt.executeUpdate();
            System.out.println("Existing record (if any) deleted successfully!");

            String insertSQL = "INSERT INTO Student (SSN, FirstName, MiddleName, LastName, DOB, Street, Phone, Zipcode, deptID) VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?)";
            PreparedStatement insertStmt = conn.prepareStatement(insertSQL);
            insertStmt.setString(1, "111222333");
            insertStmt.setString(2, "Philip");
            insertStmt.setString(3, "David Charles");
            insertStmt.setString(4, "Collins");
            insertStmt.setString(5, "1951-01-30"); // format: YYYY-MM-DD
            insertStmt.setString(6, "NA");
            insertStmt.setString(7, "NA");
            insertStmt.setString(8, "NA");
            insertStmt.setInt(9, 1234);
            insertStmt.executeUpdate();
            System.out.println("Record inserted successfully!");

            String updateSQL = "UPDATE Student SET Zipcode = ? WHERE SSN = ?";
            PreparedStatement updateStmt = conn.prepareStatement(updateSQL);
            updateStmt.setString(1, "92126");
            updateStmt.setString(2, "111222333");
            updateStmt.executeUpdate();
            System.out.println("Record updated successfully!");

            conn.close();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```
## My Flowchart
![Database 13-14 1](https://github.com/user-attachments/assets/3c57815b-e9bb-43e4-a134-e6252e3e9715)

## Challenges Faced

## My Assignment Video Link:
