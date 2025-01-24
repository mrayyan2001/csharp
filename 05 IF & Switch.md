# C# Tutorial: Enums, Type Conversions, and Decision Structures

## 1. Enum Conversions

### Enum <--> String

#### 1. Convert Enum to String:

```csharp
Services service = Services.Const;
string serviceName = service.ToString(); // "Const"
```

#### 2. Convert String to Enum:

```csharp
Services service = (Services)Enum.Parse(typeof(Services), "Invoice");
```

### Enum <--> Int

#### 1. Convert Enum to Int:

```csharp
int serviceValue = (int)Services.Const;
```

#### 2. Convert Int to Enum:

```csharp
Services service = (Services)3;
```

## 2. Decision Structures

### If-ElseIf-Else Example:

```csharp
Console.Write("Please Enter Mark: ");
float mark = Convert.ToSingle(Console.ReadLine());

if (mark >= 50)
{
    if (mark < 69) {
        Console.WriteLine("Poor");
    }
    else if (mark < 74) {
        Console.WriteLine("Good");
    }
    else if (mark < 84) {
        Console.WriteLine("Very Good");
    }
    else {
        Console.WriteLine("Excellent");
    }
}
else {
    Console.WriteLine("Failed");
}
```

### Optimized If-ElseIf-Else:

```csharp
Console.Write("Please Enter Mark: ");
float mark = Convert.ToSingle(Console.ReadLine());

if (mark < 50) {
    Console.WriteLine("Failed");
} else if (mark < 69) {
    Console.WriteLine("Poor");
} else if (mark < 74) {
    Console.WriteLine("Good");
} else if (mark < 84) {
    Console.WriteLine("Very Good");
} else if (mark <= 100) {
    Console.WriteLine("Excellent");
}
```

### Boolean Check using If-Else:

```csharp
Console.Write("Please Enter Mark: ");
float mark = Convert.ToSingle(Console.ReadLine());
bool isPassed = mark >= 50;

Console.WriteLine($"Is Passed? {isPassed}");
```

## 3. Switch Statement

### Example: Service Selection

```csharp
Console.WriteLine("Please Select One of The Following Services");
Console.WriteLine("1- Pay_Invoice");
Console.WriteLine("2- Recharge_Credit");
Console.WriteLine("3- Quires");
Console.WriteLine("4- New_Purches");
Console.Write("Enter The Service Number: ");
int num = Convert.ToInt32(Console.ReadLine());

switch ((Services)num)
{
    case Services.Pay_Invoice:
        Console.Write("Please Enter Invoice Id: ");
        Console.ReadLine();
        goto case Services.PaymentGateWay;
    case Services.Recharge_Credit:
        Console.Write("Please Enter Mobile Number: ");
        Console.ReadLine();
        Console.Write("Please Enter Recharge Amount: ");
        Console.ReadLine();
        goto case Services.PaymentGateWay;
    case Services.Quires:
        Console.WriteLine("Sorry, this service is unavailable");
        break;
    case Services.New_Purches:
        Console.Write("Please Enter Service Type: ");
        Console.ReadLine();
        Console.WriteLine("Price Is 10 JD. Do you want to proceed?");
        Console.ReadLine();
        Console.WriteLine($"Here is your Invoice ID: {new Random().Next()}");
        goto case Services.PaymentGateWay;
    case Services.PaymentGateWay:
        GetPaymentInfoFromUser();
        break;
    default:
        Console.WriteLine("Invalid Service Number");
        break;
}

void GetPaymentInfoFromUser()
{
    Console.Write("Please Enter Credit Card Number: ");
    Console.ReadLine();
    Console.Write("Please Enter Credit Card CVV2 Code: ");
    Console.ReadLine();
    Console.WriteLine("Thank You");
}

enum Services
{
    Pay_Invoice = 1,
    Recharge_Credit = 2,
    Quires = 3,
    New_Purches = 4,
    PaymentGateWay = 8225
}
```

## 4. Alternative Switch Expression Syntax

```csharp
string serviceName = num switch
{
    1 => "Pay_Invoice",
    2 => "Recharge_Credit",
    3 => "Quires",
    4 => "New_Purches",
    _ => "Invalid Service Number"
};
Console.WriteLine(serviceName);
```
