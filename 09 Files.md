# Files

## **1. Creating, Writing, and Reading Files**

### **Creating and Writing to a File**

```csharp
string pathForWrite = @"C:\Users\USER\Desktop\students-addx.txt";

// Create and write to a file
var fsForWrite = File.Create(pathForWrite);
var stream = new StreamWriter(fsForWrite);

// Example of writing each line with an additional string "- x"
string path = @"C:\Users\USER\Desktop\students.txt";
var fs = File.OpenRead(path);
var stremer = new StreamReader(fs);
string line;
while ((line = stremer.ReadLine()) != null)
{
    stream.WriteLine(line + " - x");
}

// Clean up resources
stremer.Dispose();
stremer.Close();
fs.Dispose();
fs.Close();
stream.Dispose();
stream.Close();
fsForWrite.Dispose();
fsForWrite.Close();
```

### **Checking if a File Exists**

```csharp
string path = @"C:\Users\USER\Desktop\students.txt";

// Check if file exists
bool fileExists = File.Exists(path);
Console.WriteLine($"File exists: {fileExists}");
```

### **Deleting a File**

```csharp
string path = @"C:\Users\USER\Desktop\students.txt";

// Delete the file
File.Delete(path);
```

---

## **2. Writing User Input to a File**

### **Write Data Entered by User to File**

```csharp
string path = @"C:\Users\USER\Desktop\students.txt";

// Open file for writing
var fs = File.OpenWrite(path);
var sw = new StreamWriter(fs);

Console.Write("Please Enter The First Student Name: ");
sw.WriteLine(Console.ReadLine());

Console.Write("Please Enter The Second Student Name: ");
sw.WriteLine(Console.ReadLine());

// Clean up resources
sw.Dispose();
sw.Close();
fs.Dispose();
fs.Close();
```

---

## **3. Reading Data from a File**

### **Reading File and Displaying Its Content**

```csharp
string path = @"C:\Users\USER\Desktop\students.txt";

// Open file for reading
var fs = File.OpenRead(path);
var stremer = new StreamReader(fs);

string line;
while ((line = stremer.ReadLine()) != null)
{
    Console.WriteLine(line);
}

// Clean up resources
stremer.Dispose();
stremer.Close();
fs.Dispose();
fs.Close();
```

---

## **4. File Operations - Read, Write, Max, Min, Sum**

### **Working with a List of Numbers**

```csharp
List<int> numbers = new List<int>();

// Read numbers from user
for (int i = 0; i < 5; i++)
{
    Console.Write("Please Enter A Number: ");
    numbers.Add(Convert.ToInt32(Console.ReadLine()));
}

string path = @"C:\Users\USER\Desktop\numbers.txt";

// Create and write data to file
var fsForWrite = File.Create(path);
var stream = new StreamWriter(fsForWrite);
stream.WriteLine("The Inserted Source:");
stream.Write("[ ");
for (int i = 0; i < 5; i++)
{
    stream.Write(numbers[i] + " ,");
    if (i == 4)
    {
        stream.Write(numbers[i]);
    }
}
stream.Write("] ");
stream.WriteLine($"The Max Value = {numbers.Max()}");
stream.WriteLine($"The Min Value = {numbers.Min()}");
stream.WriteLine($"The Summation of Values = {numbers.Sum()}");

// Clean up resources
stream.Dispose();
stream.Close();
fsForWrite.Dispose();
fsForWrite.Close();
```

---

## **5. Appending Data to a File**

### **Appending Single Lines to a File**

```csharp
string path = @"C:\Users\USER\Desktop\students.txt";

Console.Write("Please Enter The First Student Name: ");
File.AppendAllText(path, Console.ReadLine() + "\n");

Console.Write("Please Enter The Second Student Name: ");
File.AppendAllText(path, Console.ReadLine() + "\n");
```

### **Appending Multiple Lines to a File**

```csharp
string path = @"C:\Users\USER\Desktop\students.txt";
List<string> names = new List<string>();

Console.Write("Please Enter The First Student Name: ");
names.Add(Console.ReadLine());

Console.Write("Please Enter The Second Student Name: ");
names.Add(Console.ReadLine());

File.AppendAllLines(path, names);
```

---

## **6. File Copying and Moving**

### **Copying Data from One File to Another**

```csharp
string sourceFile = @"C:\Users\USER\Desktop\numbers.txt";
string destinationFile = @"C:\Users\USER\Desktop\result.txt";

// Open source and destination files
var sourceFileStream = File.OpenRead(sourceFile);
var destinationFileStream = File.Create(destinationFile);

// Copy data from source to destination
sourceFileStream.CopyTo(destinationFileStream);

// Clean up resources
sourceFileStream.Dispose();
sourceFileStream.Close();
destinationFileStream.Dispose();
destinationFileStream.Close();
```

### **Checking, Copying, Moving, and Deleting Files**

#### **Reading Data from File and Handling Missing Files**

```csharp
string filePath = @"C:\Users\USER\Desktop\Students.txt";
string desPath = @"D:\Jasser - Files\(12) Helpers\NewHelperStudents.txt";
string copyPath = @"C:\Users\USER\Desktop\Students-2.txt";

// Check if file exists
if (File.Exists(filePath))
{
    FileStream fileStream = File.OpenRead(filePath);
    StreamReader streamReader = new StreamReader(fileStream);
    string line;
    while ((line = streamReader.ReadLine()) != null)
    {
        Console.WriteLine(line);
    }
    streamReader.Dispose();
    fileStream.Dispose();
}
else
{
    // If file doesn't exist, copy, delete, or move it
    File.Copy(filePath, copyPath);
    File.Delete(filePath);
    File.Move(filePath, desPath);
    Console.WriteLine("File does not exist.");
}
```

#### **Writing User Input to a File**

```csharp
var path = @"C:\Users\USER\Desktop\Numbers.txt";
var fileStream = File.Create(path);
StreamWriter streamWriter = new StreamWriter(fileStream);

for (int i = 0; i < 10; i++)
{
    Console.Write("Please Enter A Number: ");
    streamWriter.WriteLine(Console.ReadLine());
}

streamWriter.Dispose();
fileStream.Dispose();
```

---

## **7. Additional File Operations**

### **Reading, Creating, Updating, Copying, and Deleting Files**

```csharp
// File paths for different operations
var filePath = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Marks.txt"; // For Read
var filePath2 = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Names.txt"; // For Write/Create
var filePath3 = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Names.txt"; // For Update
var filePath4 = @"C:\Users\C-ROAD\OneDrive - Dragonsoft\Desktop\Students.txt"; // For Copy

// 1. Read File
using FileStream fs = File.OpenRead(filePath);
using var sr = new StreamReader(fs);
string line;
while ((line = sr.ReadLine()) != null)
{
    Console.WriteLine(line);
}

// 2. Create File
using FileStream fs2 = File.Create(filePath2);
using var sw = new StreamWriter(fs2);
sw.WriteLine("Jasser");
sw.WriteLine("Ahmad");
sw.WriteLine("Khaled");
sw.WriteLine("Marwa");

// 3. Update File
for (int i = 9; i > 0; i--)
{
    File.AppendAllText(filePath3, Console.ReadLine() + "\n");
}

// 4. Copy Files
using var fs4 = new FileStream(filePath4, FileMode.OpenOrCreate); // Destination
using var fsSource = new FileStream(filePath, FileMode.Open); // Source
using var fsSource2 = new FileStream(filePath2, FileMode.Open); // Source
fsSource.CopyTo(fs4);
fsSource2.CopyTo(fs4);

// 5. Delete Files
File.Delete(filePath);
File.Delete(filePath2);
```

---

## **File Operations Summary**

- **Reading Files**: Use `StreamReader` to read data line by line.
- **Writing Files**: Use `StreamWriter` to write data to a file.
- **Appending Data**: Use `File.AppendAllText` or `File.AppendAllLines` to append to existing files.
- **Deleting Files**: Use `File.Delete` to delete files.
- **Copying Files**: Use `File.CopyTo` to copy data from one file to another.
- **Moving Files**: Use `File.Move` to move files to a different location.
- **Checking for Existence**: Use `File.Exists` to check if a file exists before performing operations.

---
