# **Arrays in C#**

Arrays store multiple values of the same data type in a single variable. C# supports **one-dimensional**, **multi-dimensional**, and **jagged arrays**.

---

## **1D Arrays (One-Dimensional Arrays)**

### **Declaring and Initializing Arrays**

```csharp
// Declaration
int[] ints;

// Static initialization
int[] numbers = { 78, 86, 79, 61, 59 };

// Dynamic initialization
int[] ints1 = new int[5];

// Hybrid Model (declaration + initialization)
int[] numbers3 = new int[5] { 11, 12, 13, 14, 19 };
```

### **Reading Values from Arrays**

```csharp
// A - Accessing elements using an index
Console.WriteLine(numbers3[3]);  // Output: 14

// B - Storing array values in variables
int x = numbers3[0];

// C - Assigning an array value to another variable
ints1[4] = numbers3[1];

// Reassigning an element
numbers3[3] = 24;  // Changing index 3 from 14 to 24
```

---

### **Reading User Input and Calculating Average**

Here’s an example where we read 5 integer values from the user, sort them in descending order, and calculate the average:

```csharp
// Read 5 integer values from the user
int[] intes = new int[5];
Console.Write("Please Enter The Value # 1 : ");
intes[0] = Convert.ToInt32(Console.ReadLine());
Console.Write("Please Enter The Value # 2 : ");
intes[1] = Convert.ToInt32(Console.ReadLine());
Console.Write("Please Enter The Value # 3 : ");
intes[2] = Convert.ToInt32(Console.ReadLine());
Console.Write("Please Enter The Value # 4 : ");
intes[3] = Convert.ToInt32(Console.ReadLine());
Console.Write("Please Enter The Value # 5 : ");
intes[4] = Convert.ToInt32(Console.ReadLine());

// Sorting the array in descending order
Array.Sort(intes);
Array.Reverse(intes);

// Calculate the average
double sum = intes[0] + intes[1] + intes[2] + intes[3] + intes[4];
Console.WriteLine($"Average = {sum / 5}");
```

### **Array Operations**

```csharp
// Array Declaration and Initialization
int[] ints; // Declaration (null instance, reserves reference)
int[] numbers = new int[5]; // Dynamic initialization
int[] numbers2 = { 25, 13, 85, 12 }; // Static initialization with values
int[] numbers3 = new int[3] { -1, -1, -1 }; // Dynamic array with specific values

// Update (Reassign)
numbers[0] = 17;

// Read a value
Console.WriteLine(numbers2[0]);  // Output: 25

// Get Length (Number of elements in the array)
Console.WriteLine(numbers.Length);  // Output: 5

// Sorting the array elements in ascending order
Array.Sort(numbers);

// Reversing the array elements
Array.Reverse(numbers);

// Resetting the array to default values
Array.Clear(numbers, 0, numbers.Length); // Resets all elements to 0

// Filling the array with a specific value
Array.Fill(numbers, -1); // Sets all elements in the array to -1
```

---

## **2D Arrays (Multi-Dimensional Arrays)**

A **2D array** is a matrix-like structure with rows and columns.

### **Declaring a 2D Array**

```csharp
// Declaring a 2D array with 4 rows and 6 columns
double[,] numbers = new double[4, 6];

Random random = new Random();
```

### **Filling the 2D Array**

#### **1. Filling the First and Third Rows with Static Values**

```csharp
// First row
numbers[0, 0] = 14; numbers[0, 1] = 14; numbers[0, 2] = 14;
numbers[0, 3] = 14; numbers[0, 4] = 14; numbers[0, 5] = 14;

// Third row
numbers[2, 0] = 14; numbers[2, 1] = 14; numbers[2, 2] = 14;
numbers[2, 3] = 14; numbers[2, 4] = 14; numbers[2, 5] = 14;
```

#### **2. Filling the Second Row with Random Values**

```csharp
numbers[1, 0] = random.Next(1, 100);
numbers[1, 1] = random.Next(1, 100);
numbers[1, 2] = random.Next(1, 100);
numbers[1, 3] = random.Next(1, 100);
numbers[1, 4] = random.Next(1, 100);
numbers[1, 5] = random.Next(1, 100);
```

#### **3. Filling the Fourth Row with User Input**

```csharp
numbers[3, 0] = Convert.ToDouble(Console.ReadLine());
numbers[3, 1] = Convert.ToDouble(Console.ReadLine());
numbers[3, 2] = Convert.ToDouble(Console.ReadLine());
numbers[3, 3] = Convert.ToDouble(Console.ReadLine());
numbers[3, 4] = Convert.ToDouble(Console.ReadLine());
numbers[3, 5] = Convert.ToDouble(Console.ReadLine());
```

---
