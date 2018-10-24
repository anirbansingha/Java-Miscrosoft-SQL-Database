# Java-Miscrosoft-SQL-Database.

Beginner: This article shows how to connect Microsoft SQL database using Java.

Prerequisites
        
Download the Microsoft JDBC Driver 6.0 for SQL Server, a Type 4 JDBC driver that provides database connectivity through the standard JDBC application program interfaces (APIs) available in Java Platform, Enterprise Editions.

https://www.microsoft.com/en-us/download/details.aspx?id=11774

Download the JAR files to your computer.
Open NetBeans and right-click on the project name in the Projects tab.
Select Properties.
Select Libraries.
Click the Add Jar/Folder button.
Navigate to the directory where the downloaded JAR files are, select the Jar and click OK

# Java-CODE
package sql;

import java.sql.Connection;

import java.sql.DriverManager;

import java.sql.ResultSet;

import java.sql.SQLException;

import java.sql.Statement;

/**
 *
 * @author Administrator
 */
public class SQL {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        
        try {
            
 Class.forName("com.microsoft.sqlserver.jdbc.SQLServerDriver");
 
 String url="jdbc:sqlserver://localhost:1433;databaseName=MYDATABASE;integratedSecurity=true";
 
 Connection con = DriverManager.getConnection(url); 
 
 Statement stmt = con.createStatement();
 
 String sql = "SELECT * FROM MYDATABASE.dbo.mms_table";
 
ResultSet rs = stmt.executeQuery(sql);

while (rs.next()) {

     System.out.println("Hello");   
     
    System.out.println(rs.getString("FirstName") + " " + rs.getString("LastName"));
    
            }
            
            
            

    }
        
        catch(Exception e)
        {
            
        }
    }
}
