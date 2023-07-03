# C++

## **C++ Syntax**

### **Variables**

```cpp
int x = 10; // declaration and initialization
int y; // declaration without initialization
y = 20; // initialization after declaration
```

### **Data Types**

| Data Type | Description | Example |
| --- | --- | --- |
| bool | Boolean | true, false |
| char | Character | 'a', 'b' |
| int | Integer | 1, 2, -3 |
| float | Floating-point number | 3.14, -2.5 |
| double | Double precision floating-point number | 3.14159, -2.71828 |
| string | String | "hello", "world" |

### **Operators**

| Operator | Description | Example |
| --- | --- | --- |
| + | Addition | x + y |
| - | Subtraction | x - y |
| * | Multiplication | x * y |
| / | Division | x / y |
| % | Modulo (remainder) | x % y |
| = | Assignment | x = 5 |
| == | Equality | x == y |
| != | Inequality | x != y |
| < | Less than | x < y |
| > | Greater than | x > y |
| <= | Less than or equal to | x <= y |
| >= | Greater than or equal to | x >= y |
| && | Logical AND | x > 0 && x < 10 |
| ` |  | ` |
| ! | Logical NOT | !(x == y) |

### **Control Structures**

### Conditional Statements

```
c++Copy code
if (x > y) {
    // do something
} else if (x < y) {
    // do something else
} else {
    // do something different
}

```

### Loops

### **`while` Loop**

```cpp
while (x < 10) {
    // do something
    x++;
}
```

### **`do-while` Loop**

```cpp
do {
    // do something
    x++;
} while (x < 10);
```

### **`for` Loop**

```cpp
for (int i = 0; i < 10; i++) {
    // do something
}
```

### **Functions**

```cpp
int add(int x, int y) {
    return x + y;
}

int result = add(3, 4);
```

### **Pointers**

```cpp
int x = 10;
int* p = &x; // p points to the address of x
cout << *p << endl; // prints the value of x (10)
```

### **Arrays**

```cpp
int arr[5] = {1, 2, 3, 4, 5};
cout << arr[0] << endl; // prints 1
cout << arr[4] << endl; // prints 5
```

### **Classes**

```cpp
class MyClass {
public:
    void sayHello() {
        cout << "Hello!" << endl;
    }
private:
    int x;
};
```

## Standard Library

### Input/Output

```cpp
#include <iostream>using namespace std;

int main() {
    int x;
    cin >> x; // read input from user
    cout << "The value of x is: " << x << endl; // output to console
    return 0;
}
```

### Strings

```cpp
#include <string>using namespace std;

string s = "hello";
cout << s.length() << endl; // prints 5
cout << s[1] << endl; // prints 'e'
```

### Vectors

```cpp

#include <vector>using namespace std;

vector<int> v = {1, 2, 3, 4, 5};
v.push_back(6);
cout << v.size() << endl; // prints 6
cout << v[2] << endl; // prints 3
```

### Iterators

```cpp
#include <vector>#include <iostream>using namespace std;

vector<int> v = {1, 2, 3, 4, 5};

for (vector<int>::iterator it = v.begin(); it != v.end(); it++) {
    cout << *it << endl;
}
```

### Algorithms

```cpp
c++Copy code
#include <algorithm>#include <vector>using namespace std;

vector<int> v = {5, 2, 7, 4, 1};

sort(v.begin(), v.end()); // sort the vector

if (binary_search(v.begin(), v.end(), 7)) { // check if element exists in vector
    cout << "7 found in vector" << endl;
}
```

### File I/O

```cpp
#include <fstream>using namespace std;

ofstream myfile;
myfile.open("example.txt");
myfile << "Writing to file" << endl;
myfile.close();
```

### Math

```cpp
#include <cmath>using namespace std;

double x = 3.14;
cout << cos(x) << endl; // prints -0.999998
cout << pow(x, 2) << endl; // prints 9.8596
```

### Time

```cpp

#include <chrono>#include <iostream>using namespace std;
using namespace std::chrono;

auto start = high_resolution_clock::now();

// do some operation

auto stop = high_resolution_clock::now();
auto duration = duration_cast<microseconds>(stop - start);

cout << "Time taken by function: " << duration.count() << " microseconds" << endl;
```
