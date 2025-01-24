# **Data Structures in C#**

C# provides various data structures such as **LinkedLists, Lists, Queues, and Stacks** to efficiently store and manipulate data.

---

## **1. LinkedList<T> (Doubly Linked List)**

A `LinkedList<T>` is a **doubly linked list** where each node contains a value and references to the next and previous nodes.

### **Declaration and Initialization**

```csharp
// Null declaration
LinkedList<long> longs2;

// Empty LinkedList
LinkedList<long> longs3 = new LinkedList<long>();

// Static initialization
LinkedList<long> longs = new LinkedList<long>(new long[] { 11, 25, 35, 25 });
```

### **Reading Values**

```csharp
Console.WriteLine(longs.First.Value);   // First element
Console.WriteLine(longs.Last.Value);    // Last element
Console.WriteLine(longs.Find(25));      // First node with value 25
Console.WriteLine(longs.FindLast(25));  // Last node with value 25
Console.WriteLine(longs.ElementAt(0));  // Element at index 0
```

### **Inserting Elements**

```csharp
longs.AddFirst(25);             // Add 25 at the beginning
longs.AddLast(25);              // Add 25 at the end
longs.AddAfter(longs.Find(16), 17);  // Insert 17 after 16
longs.AddBefore(longs.Find(11), 17); // Insert 17 before 11
```

### **Updating Elements**

```csharp
longs.Last.Value = 15; // Update last element
```

### **Operations**

```csharp
longs.Clear(); // Remove all elements
```

---

## **2. List<T> (Dynamic Array)**

A `List<T>` is a **resizable array** that provides dynamic memory allocation and many useful methods.

### **Declaration and Initialization**

```csharp
List<double> random = new List<double> { 1.8, 0.15, 0.25, 0.35 };
List<double> random1 = new List<double>(); // Empty list
List<int> ints = new List<int> { 1, 2, 3, 4 };
```

### **Inserting Elements**

```csharp
Console.WriteLine("Before Add: " + ints.Count);
ints.Add(1);
Console.WriteLine("Before Append: " + ints.Count);
ints = ints.Append(2).ToList();
Console.WriteLine("Before Insert: " + ints.Count);
ints.Insert(6, 9); // Insert at index 6
Console.WriteLine("Final Count: " + ints.Count);
```

#### **Adding Multiple Elements**

```csharp
random1.Add(0.10);
random1.AddRange(random);
random1.InsertRange(2, new List<double> { 0.18, 0.65, 0.75 });
```

### **Reading Values**

```csharp
Console.WriteLine(random1[0]);         // Access element by index
Console.WriteLine(random1.ElementAt(5)); // Access element at index 5
```

### **Updating Elements**

```csharp
random1[0] = 1.8; // Reassign value at index 0
```

### **Removing Elements**

```csharp
random1.RemoveAt(0);       // Remove element at index 0
random1.RemoveRange(2, 3); // Remove 3 elements starting from index 2
random1.Clear();           // Remove all elements
```

---

### **Operations on Lists**

```csharp
// List Declaration and Initialization
List<string> names; // Null list

// Error: Null Reference Exception if accessed without initialization

// Initialization
List<double> numbers = new List<double>(); // Dynamic initialization
List<double> marks = new List<double>() { 17.5, 21.3, 12, 3 }; // Static initialization

// Get Length
Console.WriteLine(numbers.Count);  // Output: 0 (as it's empty)

// Read Elements
Console.WriteLine(marks[0]);        // Output: 17.5
Console.WriteLine(marks.ElementAt(2)); // Output: 12

// Reassigning values
marks[1] = 25;  // Changing value at index 1

// Insert Single Values
marks.Add(36);        // Adds 36 to the end
marks.Insert(1, 25);  // Inserts 25 at index 1

// Insert Collection / Another List
marks.AddRange(numbers);       // Adds elements of 'numbers' list to 'marks'
marks.InsertRange(2, numbers); // Inserts elements of 'numbers' list starting at index 2

// Remove Elements
marks.RemoveAt(2);   // Removes element at index 2
marks.RemoveRange(2, 3); // Removes 3 elements starting from index 2
marks.Clear();         // Removes all elements

// Operations
marks.Sort();          // Sorts in ascending order
Console.WriteLine(marks.IndexOf(25));   // Finds first index of 25
Console.WriteLine(marks.LastIndexOf(25)); // Finds last index of 25
Console.WriteLine(marks.Contains(25));  // Returns true if 25 exists
```

---

## **3. Queue<T> (FIFO Collection)**

A `Queue<T>` follows the **FIFO (First-In-First-Out)** principle, where elements are dequeued in the order they were added.

### **Declaration and Initialization**

```csharp
Queue<int> ints2; // Null queue
Queue<int> ints = new Queue<int>(); // Empty queue
Queue<int> ints3 = new Queue<int>(new int[] { 14, 15, 16 });
```

### **Properties**

```csharp
Console.WriteLine(ints.Count);  // Get queue length
Console.WriteLine(ints3.Count); // Get queue length
```

### **Inserting Elements**

```csharp
ints3.Enqueue(5); // Add element at the end
```

### **Reading Values**

```csharp
Console.WriteLine(ints3.Peek());      // Peek first element (14)
Console.WriteLine(ints3.ElementAt(2));// Get element at index 2 (16)
Console.WriteLine(ints3.Dequeue());   // Remove and return first element (14)
```

### **Removing Elements**

```csharp
ints3.Clear(); // Remove all elements
```

### **Searching**

```csharp
Console.WriteLine(ints3.Contains(5)); // Check if queue contains 5
```

---

## **4. Stack<T> (LIFO Collection)**

A `Stack<T>` follows the **LIFO (Last-In-First-Out)** principle, where elements are removed in reverse order of insertion.

### **Declaration and Initialization**

```csharp
Stack<int> ints2; // Null stack
Stack<int> ints = new Stack<int>(); // Empty stack
Stack<int> ints3 = new Stack<int>(new int[] { 14, 15, 16 });
```

### **Properties**

```csharp
Console.WriteLine(ints.Count);  // Get stack length
Console.WriteLine(ints3.Count); // Get stack length
```

### **Inserting Elements**

```csharp
ints3.Push(5); // Push element onto stack
```

### **Reading Values**

```csharp
Console.WriteLine(ints3.Peek());      // Peek top element (16)
Console.WriteLine(ints3.ElementAt(2));// Get element at index 2 (14)
Console.WriteLine(ints3.Pop());       // Remove and return top element (16)
```

### **Removing Elements**

```csharp
ints3.Clear(); // Remove all elements
```

### **Searching**

```csharp
Console.WriteLine(ints3.Contains(5)); // Check if stack contains 5
```

---
