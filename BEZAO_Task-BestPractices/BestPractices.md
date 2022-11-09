## 15 Best Coding Practices to Observe while Coding  


## 1. Constants should always be declared in UPPER_CASE.

``` 
// Correct
public const int MIN_AGE = 18;
public const int MAX_AGE = 60;

// Avoid
public const int Min_Age = 18;
public const int Max_Age = 60;

```

## 2. Always separate the methods, different sections of program by one space. 

```
// Correct
class Employee
{
private int employeeId { get; set; }

public void PrintDetails()
{
//------------
}
}

// Avoid
class Employee
{

private int employeeId { get; set; }



public void PrintDetails()
{
//------------
}

}

```



## 3. Do not use Underscores in identifiers. Exception: you can prefix private static variables with an underscore.

```
// Correct
public DateTime clientAppointment;
public TimeSpan timeLeft;
 
// Avoid
public DateTime client_Appointment;
public TimeSpan time_Left;
 
// Exception
private DateTime _registrationDate;

```


##  4. Use predefined type names instead of system type names like Int16, Single, UInt64, etc

```
// Correct
string firstName;
int lastIndex;
bool isSaved;
 
// Avoid
String firstName;
Int32 lastIndex;
Boolean isSaved;
```


## 5. Prefix interfaces with the letter I.  Interface names are noun (phrases) or adjectives.
```
public interface IShape
{
}
public interface IShapeCollection
{
}
public interface IGroupable
{
}
```

## 6. Vertically align curly brackets.

```
// Correct
class Program
{
    static void Main(string[] args)
    {
    }
}
```

## 7. Try to avoid complex if-else statements for null checks like in the following:

```
// Avoid
if (something != null)
{
    if (other != null)
    {
        return whatever;
    }
    else 
    {
        return string.empty;
    }
}
else
{
    return string.empty;
}

// Correct
return something?.other?.whatever ?? string.empty;

```

## 8. Always use the using keyword when working with disposable types. It automatically disposes the object when program flow leaves the scope. 

```
using(var conn = new SqlConnection(connectionString))
{
    // use the connection and the stream
    using (var dr = cmd.ExecuteReader())
    {
     //
    }
}
```

## 9. Avoid the use of System data types and prefer using the Predefined data types.

```
// Correct
int employeeId;
string employeeName;
bool isActive;
 

// Avoid
Int32 employeeId;
String employeeName;
Boolean isActive;
```


## 10. Avoid the use of underscore while naming identifiers  

```
// Correct
public DateTime fromDate;
public String firstName;
 

// Avoid
public DateTime from_Date;
public String first_Name;
```

## 11. Use the concise syntax when you initialize arrays on the declaration line. In the following example, note that you can't use var instead of string[].

```
string[] vowels1 = { "a", "e", "i", "o", "u" };

// If you use explicit instantiation, you can use var.

var vowels2 = new string[] { "a", "e", "i", "o", "u" };
```

## 12. Use Func<> and Action<> instead of defining delegate types. In a class, define the delegate method.

```
public static Action<string> ActionExample1 = x => Console.WriteLine($"x is: {x}");

public static Action<string, string> ActionExample2 = (x, y) => 
    Console.WriteLine($"x is: {x}, y is {y}");

public static Func<string, int> FuncExample1 = x => Convert.ToInt32(x);

public static Func<int, int, int> FuncExample2 = (x, y) => x + y;
```

## 13. Do not use Underscores in identifiers.
Exception: you can prefix private static variables with an underscore.

```
// Correct
public DateTime clientAppointment;
public TimeSpan timeLeft;
 
// Avoid
public DateTime client_Appointment;
public TimeSpan time_Left;
 
// Exception
private DateTime _registrationDate;
```

## 14. Avoid using Abbreviations.
Exceptions: abbreviations commonly used as names, such as Id, Xml, Ftp, Uri

```
// Correct
UserGroup userGroup;
Assignment employeeAssignment;
 
// Avoid
UserGroup usrGrp;
Assignment empAssignment;
 
// Exceptions
CustomerId customerId;
XmlDocument xmlDocument;
FtpHelper ftpHelper;
UriPart uriPart;
```

## 15. Do not use Screaming Caps for constants or readonly variables

```
// Correct
public static const string ShippingType = "DropShip";
 
// Avoid
public static const string SHIPPINGTYPE = "DropShip";
```