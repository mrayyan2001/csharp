# Files & Methods

---

## **File Operations**

### **Reading from a File**

```csharp
var filePath = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Marks.txt";
using FileStream fs = File.OpenRead(filePath);
using var sr = new StreamReader(fs);

string line;
while ((line = sr.ReadLine()) != null)
{
    Console.WriteLine(line);
}
```

### **Creating a File**

```csharp
var filePath2 = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Names.txt";
using FileStream fs2 = File.Create(filePath2);
using var sw = new StreamWriter(fs2);
sw.WriteLine("Jasser");
sw.WriteLine("Ahmad");
sw.WriteLine("Khaled");
sw.WriteLine("Marwa");
```

### **Updating a File**

```csharp
var filePath3 = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Names.txt";
for (int i = 9; i > 0; i--)
{
    File.AppendAllText(filePath3, Console.ReadLine() + "\n");
}
```

### **Copying Files**

```csharp
var filePath4 = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Students.txt";
using var fs4 = new FileStream(filePath4, FileMode.OpenOrCreate);  // Destination file
using var fs = new FileStream(filePath, FileMode.Open);  // Source file
using var fs2 = new FileStream(filePath2, FileMode.Open);  // Source file

fs.CopyTo(fs4);
fs2.CopyTo(fs4);
```

### **Deleting Files**

```csharp
File.Delete(filePath);
File.Delete(filePath2);
```

---

## **List Manipulations**

### **Generate Random Numbers and Order Them**

```csharp
List<int> numbers = new List<int>();

// Adding random numbers to the list
for (int i = 0; i < 5; i++)
{
    numbers.Add(new Random().Next(1, 21));
}

// Display original list
foreach (int i in numbers)
{
    Console.Write(i + " , ");
}
Console.WriteLine();

// Order the list in ascending order
foreach (int i in Order(numbers, true))
{
    Console.Write(i + " , ");
}
Console.WriteLine();

// Order the list in descending order
foreach (int i in Order(numbers, false))
{
    Console.Write(i + " , ");
}
```

---

## **Methods**

### **Order Method**

```csharp
List<int> Order(List<int> ints, bool isAscending)
{
    for (int i = 0; i < ints.Count; i++)
    {
        for (int j = i; j < ints.Count; j++)
        {
            if (i != j &&
                (isAscending ? ints[j] <= ints[i] : ints[j] >= ints[i]))
            {
                int temp = ints[i];
                ints[i] = ints[j];
                ints[j] = temp;
            }
        }
    }
    return ints;
}
```

### **Other Placeholder Methods (Unimplemented)**

```csharp
int ReadIntValueFromUser()
{
    throw new NotImplementedException();
}

void FindMaxAndMinForEven(List<int> ints)
{
    throw new NotImplementedException();
}

void FindMaxAndMinForOdd(List<int> ints)
{
    throw new NotImplementedException();
}

void FindDifferenceBetweenMaxAndMin(List<int> ints)
{
    throw new NotImplementedException();
}

List<int> RemoveDuplication(List<int> ints)
{
    throw new NotImplementedException();
}

void PrintList(List<int> ints)
{
    throw new NotImplementedException();
}

int FindOccurrence(List<int> ints, int value)
{
    throw new NotImplementedException();
}
```

---

## **Summary**

- **File Operations**: You demonstrated reading, writing, updating, copying, and deleting files using `FileStream` and `StreamReader/Writer`.
- **List Operations**: Generating random numbers, sorting them in ascending/descending order, and placeholders for methods to find the max/min values, remove duplicates, and print lists.
- **Methods**: Some basic utility methods (currently unimplemented) are outlined for handling user input, calculations, and list manipulations.

---
