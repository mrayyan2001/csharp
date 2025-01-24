# **Basic C# Operations**

## **Math Operations**

C# provides a `Math` class that includes various mathematical functions:

```csharp
// Exponentiation
double result = Math.Pow(25, 25);

// Square root
double sqrtValue = Math.Sqrt(9);

// Rounding and flooring
Console.WriteLine(Math.Ceiling(9.95336));  // Rounds up to 10
Console.WriteLine(Math.Round(9.9536, 3));  // Rounds to 3 decimal places
Console.WriteLine(Math.Floor(9.95336));    // Rounds down to 9
```

---

## **Random Number Generation (`random.txt`)**

The `Random` class allows generating random numbers:

```csharp
// Creating Random instances
Random r1;  // Uninitialized instance
Random r2 = new Random(); // Initialized instance

// Generating random numbers
Console.WriteLine(r2.Next());       // Any integer
Console.WriteLine(r2.Next(100));    // 0 to 99
Console.WriteLine(r2.Next(15, 100));// 15 to 99
Console.WriteLine(r2.NextDouble()); // 0.0 to 1.0
```

---

## **String Manipulation (`strings.txt`)**

The `string` class in C# provides several methods for formatting, comparing, searching, and validating strings.

### **Formatting Strings**

```csharp
string i = "Jasser Khaled Alsher";

// Changing case
i = i.ToLower();  // Converts to lowercase
i = i.ToUpper();  // Converts to uppercase

// Replacing characters
i = i.Replace("J", "Test");

// Trimming whitespace
i = i.Trim();       // Removes leading and trailing spaces
i = i.TrimStart();  // Removes leading spaces
i = i.TrimEnd();    // Removes trailing spaces

// Removing characters
i = i.Remove(2, 5); // Removes 5 characters starting from index 2
i = i.Remove(2);    // Removes all characters starting from index 2

// Reversing (not directly available, needs a workaround)
i = new string(i.Reverse().ToArray());

// Splitting strings
string[] words = i.Split(' ');

// Extracting substrings
string sub1 = i.Substring(0, 2);  // First 2 characters
string sub2 = i.Substring(2);     // All characters after index 2
```

### **Comparing Strings**

```csharp
bool isEqual = i.Equals("Jasser", StringComparison.OrdinalIgnoreCase);
bool contains = i.Contains("as");
bool startsWith = i.StartsWith("as");
bool endsWith = i.EndsWith("as");

// Converting to character array
char[] charArray = i.ToCharArray();
```

### **Searching in Strings**

```csharp
char firstChar = i.ElementAt(0);
int firstIndex = i.IndexOf("er");
int lastIndex = i.LastIndexOf("t");
```

### **Validating Strings**

```csharp
bool isNullOrEmpty = string.IsNullOrEmpty(i);
bool isNullOrWhiteSpace = string.IsNullOrWhiteSpace(i);
```

---

## **Additional C# Operations**

### **Expression Example**

```csharp
int x = 5;
int y = 6;
Console.WriteLine(x++ * y++ - + ++x - 13 + 6 / 2);
```

**Operator Precedence**:

- **Left to Right Evaluation**
  - **1. Parentheses** (Processing)
  - **2. Mathematical Operations** (`*`, `/`, `%`, `+`, `-`)
  - **3. Comparison** (`!=`, `==`, `>=`, `<=`, `>`, `<`)
  - **4. Logical Operations** (Not, And, Or)

**Operation Explanation**:

- **Process Data** to extract the result, based on the operations applied in the order of precedence.

### **Types of Operations**

1. **Linear Operation**:

   - `(Element) (Operation) (Element B)`

2. **Mixed Operation**:

   - `(Element) (Operation) (Element B) (Operation) (Element C) (Operation) (Element D)`

3. **Self Operation**:
   - `(Element A) (Operation)`

### **Variable Declaration & Initialization**

```csharp
// Declaration
datatype name;

// Initialization
datatype name = value;
```

**Numeric Types**:

```csharp
byte b1;
byte b2 = 5;

short s1;
short s2 = 17;

int i;
int i1 = 952369;

long l1;
long l2 = 258;

float f;
float f1 = 56.2f; // suffix 'f' for float

double d;
double d1 = 23.5;

decimal e1;
decimal e2 = 5.36m; // suffix 'm' for decimal
```

**Text Types**:

```csharp
char c1;
char c2 = '1';

string str1; // Reference data type
string str2 = "Test"; // Reference data type
```

**Boolean Types**:

```csharp
bool b3;
bool b4 = false;
```

---
