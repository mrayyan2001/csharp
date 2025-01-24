# Loops

## **Do-While Loop: Perform Operation at Least One Time**

### **Example: Guess the Stored Number**

```csharp
int number = new Random().Next(1, 101);  // Generate random number between 1 and 100
Console.ForegroundColor = ConsoleColor.Green;
Console.WriteLine(number);  // Display number (for testing)
Console.ForegroundColor = ConsoleColor.White;

int value;
do
{
    Console.Write("Please Guess a Number Between 1 - 100: ");
    value = Convert.ToInt32(Console.ReadLine());
} while (value != number);  // Continue until correct guess

Console.WriteLine("Correct");
```

---

## **For Loop: Iteration with Start, Condition, and Step**

### **Example: Print Multiplication Table for 3**

```csharp
int start;
for (start = 1; start <= 10; ++start)
{
    Console.WriteLine($"3 * {start} = {3 * start}");
}
Console.WriteLine(start);  // Display value after loop ends
```

---

## **For-Each Loop: Iterating Over Collections**

### **Example: Loop Through a List of Numbers**

```csharp
List<int> numbers = new List<int> { 1, 2, 3, 5, 6, 9, 12, 18 };

// Print List Items using a for loop
for (int i = 0; i < numbers.Count; i++)
{
    Console.WriteLine(numbers[i]);
}

// Print List Items using a foreach loop
foreach (int num in numbers)  // Read only values from the collection
{
    Console.WriteLine(num);
}
```

---

## **While Loop: Execute Operation Based on Condition**

### **Example: Guess the Stored Number**

```csharp
int number = new Random().Next(1, 101);  // Generate random number between 1 and 100
Console.ForegroundColor = ConsoleColor.Green;
Console.WriteLine(number);  // Display number (for testing)
Console.ForegroundColor = ConsoleColor.White;

Console.Write("Please Guess a Number Between 1 - 100: ");
int value = Convert.ToInt32(Console.ReadLine());

while (value != number)  // Continue until correct guess
{
    Console.Write("Again, Guess a Number Between 1 - 100: ");
    value = Convert.ToInt32(Console.ReadLine());
}

Console.WriteLine("Correct");
```

---

## **Summary**

- **Do-While Loop**: Ensures the operation runs at least once before checking the condition.
- **For Loop**: Provides flexibility to specify starting point, condition, and step size.
- **For-Each Loop**: Ideal for iterating over collections like lists or arrays.
- **While Loop**: Repeats operations as long as the condition remains true.

---
