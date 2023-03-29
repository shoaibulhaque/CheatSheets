# C#

Tags: CheatSheet

# **C# Cheatsheet**

## **Data Types**

### **Value Types**

| Type | Description | Range |
| --- | --- | --- |
| bool | Represents a Boolean value | true or false |
| byte | Represents an 8-bit unsigned integer | 0 to 255 |
| sbyte | Represents an 8-bit signed integer | -128 to 127 |
| char | Represents a single character | U+0000 to U+ffff |
| short | Represents a 16-bit signed integer | -32,768 to 32,767 |
| ushort | Represents a 16-bit unsigned integer | 0 to 65,535 |
| int | Represents a 32-bit signed integer | -2,147,483,648 to 2,147,483,647 |
| uint | Represents a 32-bit unsigned integer | 0 to 4,294,967,295 |
| long | Represents a 64-bit signed integer | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| ulong | Represents a 64-bit unsigned integer | 0 to 18,446,744,073,709,551,615 |
| float | Represents a single-precision floating-point number | -3.402823e38 to 3.402823e38 |
| double | Represents a double-precision floating-point number | -1.79769313486232e308 to 1.79769313486232e308 |
| decimal | Represents a decimal number | -79228162514264337593543950335 to 79228162514264337593543950335 |

### **Reference Types**

| Type | Description |  |  |  |
| --- | --- | --- | --- | --- |
| object | The ultimate base class for all types in C# |  |  |  |
| string | Represents a sequence of characters |  |  |  |
| dynamic | Enables operations to be performed on objects at runtime |  |  |  |
| var | Implicitly typed variable |  |  |  |

## **Variables**

```bash
// Declaration and initialization
<type> <identifier> = <value>;
```

```bash
// Declaration only
<type> <identifier>;
```

```bash
// Multiple variables
<type> <identifier1> = <value1>, <identifier2> = <value2>;
```

## **Operators**

| Operator | Description |
| --- | --- |
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| / | Division |
| % | Modulus |
| ++ | Increment |
| -- | Decrement |
| == | Equality |
| != | Inequality |
| > | Greater than |
| < | Less than |
| >= | Greater than or equal to |
| <= | Less than or equal to |
| && | Logical and |
| ` |  |
| ! | Logical not |
| & | Bitwise and |
| ` | ` |
| ^ | Bitwise exclusive or |
| ~ | Bitwise not |
| << | Left shift |
| >> | Right shift |
| += | Addition assignment |
| -= | Subtraction assignment |
| *= | Multiplication assignment |
| /= | Division assignment |
| %= | Modulus assignment |
| &= | Bitwise and assignment |
| ` | =` |
| ^= | Bitwise exclusive or assignment |

## **Control Flow**

### **if/else Statement**

```csharp

if (<condition>)
{
    // code to execute if the condition is true
}
else if (<condition2>)
{
    // code to execute if condition2 is true
}
else
{
    // code to execute if all conditions are false
}

```

### **switch Statement**

```csharp

switch (expression)
{
    case value1:
        // code to execute if expression equals value1
        break;
    case value2:
        // code to execute if expression equals value2
        break;
    default:
        // code to execute if expression doesn't equal any of the values
        break;
}

```

### **for Loop**

```csharp

for (int i = 0; i < 10; i++)
{
    // code to execute in each iteration of the loop
}

```

### **while Loop**

```csharp

while (condition)
{
    // code to execute while condition is true
}

```

```csharp
**do-while Loop**
do
{
    // code to execute at least once, then repeatedly while condition is true
}
while (condition);

```

```csharp

```

### **foreach Loop**

```csharp

foreach (var item in collection)
{
    // code to execute for each item in the collection
}

```

### **continue Statement**

```csharp

for (int i = 0; i < 10; i++)
{
    if (i == 5)
    {
        continue;
    }
    // code to execute in each iteration of the loop except when i equals 5
}

```

### **break Statement**

```csharp
while (true)
{
    // code to execute repeatedly
    if (condition)
    {
        break;
    }
    // more code to execute if condition is false
}

```

## **Classes and Objects**

### **Class Declaration**

```csharp
csharpCopy code
public class MyClass
{
    // fields, properties, methods, and events go here
}

```

### **Object Instantiation**

```csharp
csharpCopy code
MyClass obj = new MyClass();

```

### **Constructor**

```csharp

public class MyClass
{
    public MyClass()
    {
        // code to execute when object is created
    }
}

```

### **Field**

```csharp
csharpCopy code
public class MyClass
{
    public int myField;
}

```

### **Property**

```csharp
csharpCopy code
public class MyClass
{
    private int myField;

    public int MyProperty
    {
        get { return myField; }
        set { myField = value; }
    }
}

```

### **Method**

```csharp
csharpCopy code
public class MyClass
{
    public void MyMethod()
    {
        // code to execute when method is called
    }
}

```

### **Event**

```csharp
csharpCopy code
public class MyClass
{
    public event EventHandler MyEvent;

    protected virtual void OnMyEvent(EventArgs e)
    {
        if (MyEvent != null)
        {
            MyEvent(this, e);
        }
    }
}

```

## **Exception Handling**

### **try-catch Statement**

```csharp
csharpCopy code
try
{
    // code that might throw an exception
}
catch (Exception ex)
{
    // code to handle the exception
}

```

### **throw Statement**

```csharp
csharpCopy code
if (condition)
{
    throw new Exception("An error occurred.");
}
```

## **Data Types**

### **Value Types**

```csharp
csharpCopy code
int myInt = 42;
double myDouble = 3.14;
bool myBool = true;
char myChar = 'a';

```

### **Reference Types**

```csharp
csharpCopy code
string myString = "Hello, world!";
int[] myArray = { 1, 2, 3 };
List<int> myList = new List<int>() { 4, 5, 6 };

```

### **Implicitly Typed Local Variables**

```csharp
csharpCopy code
var myInt = 42;
var myString = "Hello, world!";

```

### **Boxing and Unboxing**

```csharp
csharpCopy code
int myInt = 42;
object boxedInt = myInt; // boxing
int unboxedInt = (int)boxedInt; // unboxing

```

## **Arrays**

### **Declaration and Initialization**

```csharp
csharpCopy code
int[] myArray = new int[3];
myArray[0] = 1;
myArray[1] = 2;
myArray[2] = 3;

int[] myArray = { 1, 2, 3 };

int[,] myMatrix = new int[2, 3];
myMatrix[0, 0] = 1;
myMatrix[0, 1] = 2;
myMatrix[0, 2] = 3;
myMatrix[1, 0] = 4;
myMatrix[1, 1] = 5;
myMatrix[1, 2] = 6;

int[,] myMatrix = { { 1, 2, 3 }, { 4, 5, 6 } };

```

### **Accessing Elements**

```csharp
csharpCopy code
int[] myArray = { 1, 2, 3 };
int firstElement = myArray[0]; // equals 1

int[,] myMatrix = { { 1, 2, 3 }, { 4, 5, 6 } };
int element = myMatrix[1, 2]; //

```

## **Strings**

### **Declaration and Initialization**

```csharp
csharpCopy code
string myString = "Hello, world!";

string myString = string.Empty;

string myString = null;

```

### **Concatenation**

```csharp
csharpCopy code
string firstName = "John";
string lastName = "Doe";
string fullName = firstName + " " + lastName; // equals "John Doe"

```

### **Formatting**

```csharp
csharpCopy code
int age = 42;
string message = string.Format("I am {0} years old.", age); // equals "I am 42 years old."

decimal price = 3.14m;
string message = string.Format("The price is {0:C}.", price); // equals "The price is $3.14."

```

### **Substrings**

```csharp
csharpCopy code
string myString = "Hello, world!";
string substring = myString.Substring(7, 5); // equals "world"

```

### **Length**

```csharp
csharpCopy code
string myString = "Hello, world!";
int length = myString.Length; // equals 13

```

### **String Comparison**

```csharp
csharpCopy code
string str1 = "Hello";
string str2 = "hello";
bool isEqual = str1.Equals(str2, StringComparison.OrdinalIgnoreCase); // equals true

```

## **LINQ**

### **Query Syntax**

```csharp
csharpCopy code
var result = from c in customers
             where c.City == "London"
             orderby c.Name ascending
             select c;

```

### **Method Syntax**

```csharp
csharpCopy code
var result = customers
    .Where(c => c.City == "London")
    .OrderBy(c => c.Name);

```

## **File I/O**

### **Writing Text to a File**

```csharp
csharpCopy code
string path = @"C:\MyFile.txt";
string text = "Hello, world!";
File.WriteAllText(path, text);

```

### **Reading Text from a File**

```csharp
csharpCopy code
string path = @"C:\MyFile.txt";
string text = File.ReadAllText(path);

```

### **Writing Binary Data to a File**

```csharp
csharpCopy code
string path = @"C:\MyFile.dat";
byte[] data = { 0x01, 0x02, 0x03 };
File.WriteAllBytes(path, data);

```

### **Reading Binary Data from a File**

```csharp
csharpCopy code
string path = @"C:\MyFile.dat";
byte[] data = File.ReadAllBytes(path);

```

# Problem Exercises

1. Write a program to calculate the sum of two integers. 
2. Write a program to calculate the average of three integers.
3. Write a program to convert a Celsius temperature to Fahrenheit.
4. Write a program to convert a Fahrenheit temperature to Celsius.
5. Write a program to check if a given integer is even or odd.
6. Write a program to check if a given integer is a prime number.
7. Write a program to find the maximum of three integers.
8. Write a program to find the minimum of three integers.
9. Write a program to swap two integers without using a temporary variable.
10. Write a program to count the number of occurrences of a given character in a string.
11. Write a program to count the number of words in a string.
12. Write a program to concatenate two strings without using the + operator.
13. Write a program to remove all vowels from a given string.
14. Write a program to reverse a string.
15. Write a program to check if a given string is a palindrome.
16. Write a program to find the length of the longest word in a string.
17. Write a program to remove duplicate characters from a string.
18. Write a program to sort an array of integers in ascending order.
19. Write a program to sort an array of integers in descending order.
20. Write a program to find the sum of all even integers in an array.
21. Write a program to find the sum of all odd integers in an array.
22. Write a program to find the average of all integers in an array.
23. Write a program to find the smallest integer in an array.
24. Write a program to find the largest integer in an array.
25. Write a program to remove all duplicates from an array.
26. Write a program to remove all odd integers from an array.
27. Write a program to remove all even integers from an array.
28. Write a program to remove all negative integers from an array.
29. Write a program to remove all positive integers from an array.
30. Write a program to concatenate two arrays.
31. Write a program to find the first occurrence of a given integer in an array.
32. Write a program to find the last occurrence of a given integer in an array.
33. Write a program to find the second-largest integer in an array.
34. Write a program to find the second smallest integer in an array.
35. Write a program to find the index of the largest integer in an array.
36. Write a program to find the index of the smallest integer in an array.
37. Write a program to find the mode of an array.
38. Write a program to find the median of an array.
39. Write a program to count the number of occurrences of a given integer in an array.
40. Write a program to reverse an array.
41. Write a program to check if an array is sorted in ascending order.
42. Write a program to check if an array is sorted in descending order.
43. Write a program to find the intersection of two arrays.
44. Write a program to find the union of two arrays.
45. Write a program to find the difference between two arrays.
46. Write a program to find the symmetric difference between two arrays.
47. Write a program to find the common elements between two arrays.
48. Write a program to find the distinct elements between two arrays.
49. Write a program to find the missing elements between two arrays.
50. Write a program to find the sum of all integers between two given integers.
