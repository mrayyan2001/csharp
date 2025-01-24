# **C# Console Input, Validation & Simple Calculator**

This tutorial demonstrates:

- **Reading input from users**
- **Validating user input**
- **Performing basic arithmetic operations**
- **Using functions for cleaner code structure**

---

## **1. User Input and Validation**

This example takes two numbers from the user, ensuring they are in a valid format and within an accepted range.

### **Code Example:**

```csharp
int num1, num2;

// Get First Number
Console.Write("Please Enter First Number: ");
bool isNum1Casted = int.TryParse(Console.ReadLine(), out num1);

// Get Second Number
Console.Write("Please Enter Second Number: ");
bool isNum2Casted = int.TryParse(Console.ReadLine(), out num2);

// Validation
bool isNum1Valid = num1 >= 0 && num1 <= 100;
bool isNum2Valid = num2 > 0 && num2 <= 100;

if (isNum1Casted && isNum2Casted && isNum1Valid && isNum2Valid)
{
    Console.WriteLine($"{num1} + {num2} = {num1 + num2}");
    Console.WriteLine($"{num1} - {num2} = {num1 - num2}");
    Console.WriteLine($"{num1} * {num2} = {num1 * num2}");
    Console.WriteLine($"{num1} / {num2} = {num1 / num2}");
    Console.WriteLine($"{num1} % {num2} = {num1 % num2}");
}
else
{
    Console.ForegroundColor = ConsoleColor.Red;
    Console.WriteLine("Invalid input: Please enter numbers between 0 and 100.");
    Console.ForegroundColor = ConsoleColor.White;
}
```

---

## **2. Improved Input Handling using Functions**

Instead of duplicating input validation code, we can **use functions** to handle input validation and calculations.

### **Code Example:**

```csharp
Calculator(ReadIntegerValueFromUser(), ReadIntegerValueFromUser());

int ReadIntegerValueFromUser()
{
    int num;
    Console.Write("Please Enter a Number: ");
    if (int.TryParse(Console.ReadLine(), out num))
    {
        return num;
    }
    else
    {
        ShowErrorMessage("Invalid format! Please enter a valid integer.");
        return ReadIntegerValueFromUser(); // Recursive call for correct input
    }
}

bool IsInScope(int num)
{
    return num > 0 && num <= 100;
}

void Calculator(int num1, int num2)
{
    if (IsInScope(num1) && IsInScope(num2))
    {
        Console.WriteLine($"{num1} + {num2} = {num1 + num2}");
        Console.WriteLine($"{num1} - {num2} = {num1 - num2}");
        Console.WriteLine($"{num1} * {num2} = {num1 * num2}");
        Console.WriteLine($"{num1} / {num2} = {num1 / num2}");
        Console.WriteLine($"{num1} % {num2} = {num1 % num2}");
    }
    else
    {
        ShowErrorMessage("One or both values are out of range (1-100).");
    }
}

void ShowErrorMessage(string error)
{
    Console.ForegroundColor = ConsoleColor.Red;
    Console.WriteLine(error);
    Console.ForegroundColor = ConsoleColor.White;
}
```

---

## **3. User Prompt & String Formatting**

Here’s how to prompt the user for input and use different **string formatting techniques**.

### **Code Example:**

```csharp
// Prompt Message
Console.ForegroundColor = ConsoleColor.Blue;
Console.WriteLine("Please Enter Your Name:");
Console.ForegroundColor = ConsoleColor.White;

string name = Console.ReadLine();

// Static Message
Console.ForegroundColor = ConsoleColor.Red;
Console.WriteLine("The End");
Console.ForegroundColor = ConsoleColor.White;

// String Concatenation
string phone = "07877008333";
Console.ForegroundColor = ConsoleColor.Green;

Console.WriteLine("Hello " + name); // Concatenation
Console.WriteLine("Hello {0}, Your Phone is {1}", name, phone); // Placeholder
Console.WriteLine($"Hello {name}, Your Phone is {phone}"); // String Interpolation

Console.ForegroundColor = ConsoleColor.White;
```

---

## **Key Takeaways**

✔ **Validation using `int.TryParse()`** prevents errors from invalid input.  
✔ **Functions (`ReadIntegerValueFromUser()`, `Calculator()`)** make the code reusable and modular.  
✔ **Error handling (`ShowErrorMessage()`)** improves the user experience.  
✔ **String formatting (`Concatenation`, `Placeholder`, `Interpolation`)** helps display dynamic messages cleanly.

---
