<h1>JDBC Connection</h1>
<p>JDBC is an acronym for Java Database Connectivity. It’s an advancement for ODBC ( Open Database Connectivity ). JDBC is an standard API specification developed in order to move data from frontend to backend. This API consists of classes and interfaces written in Java. It basically acts as an interface  or channel between your Java program and databases i.e it establishes a link between the two so that a programmer could send data from Java code and store it in the database for future use.</p>
<h2>Steps to connect to database</h2>
<ul>
<li>Import JDBC packages.
<li>Load and register the JDBC driver.
<li>Open a connection to the database.
<li>Create a statement object to perform a query.
<li>Execute the statement object and return a query resultset.
<li>Process the resultset.
<li>Close the resultset and statement objects.
<li>Close the connection.
</ul>
<img src=connection.png alt=JDBCConnection height="500" width="500">
<ol>
<li><h3>Loading the Driver</h3>
<p>To begin with, you first need load the driver or register it before using it in the program . Registration is to be done once in your program. You can register a driver in one of two ways mentioned below :

Class.forName() : Here we load the driver’s class file into memory at the runtime. No need of using new or creation of object .The following example uses Class.forName() to load the Oracle driver –
 Class.forName(“oracle.jdbc.driver.OracleDriver”);
 DriverManager.registerDriver(): DriverManager is a Java inbuilt class with a static member register. Here we call the constructor of the driver class at compile time . The following example uses DriverManager.registerDriver()to register the Oracle driver –
 DriverManager.registerDriver(new oracle.jdbc.driver.OracleDriver())</p>
 <li><h3>Create the connections</h3>
<p>After loading the driver, establish connections using :

 Connection con = DriverManager.getConnection(url,user,password)
user – username from which your sql command prompt can be accessed.
password – password from which your sql command prompt can be accessed.

con: is a reference to Connection interface.
url : Uniform Resource Locator. It can be created as follows:

String url = “ jdbc:oracle:thin:@localhost:1521:xe”
Where oracle is the database used, thin is the driver used , @localhost is the IP Address where database is stored, 1521 is the port number and xe is the service provider. All 3 parameters above are of String type and are to be declared by programmer before calling the function. Use of this can be referred from final code.</p>