# Connection with DBs 
- Java Database Connectivity (JDBC)
- An API to connect Java to DBs
- can throw a `SQLException`

###  Creating Connection
```java
// creating connection with MySQL
String url = "jdbc:mysql://localhost:3306/dbname";   
con = DriverManager.getConnection(url, "user", "password");
```

### Select
```java
// with the conection created...

String selectQuery = "SELECT column FROM table";  
PreparedStatement ps = con.prepareStatement(selectQuery);

// executeQuery and return a ResultSet Object
ResultSet rs = ps.executeQuery();

// print the results one by one
while(rs.next()) {  
	System.out.println(rs.getString("column")); 
}

// close the connection
con.close();
```

### Inserts, updates, Deletes
```java
String insertQuery = "INSERT INTO table(column) VALUES (?)";  
PreparedStatement ps = con.prepareStatement(insertQuery); 

// set the "?" value
ps.setString(1, "value");  

// exec and return the number of rows affected
int rows = ps.executeUpdate();  
System.out.println(rows); // 1

// close connection
con.close();
```

