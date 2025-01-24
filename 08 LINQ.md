# **LINQ in C#**

LINQ (Language-Integrated Query) allows querying data in various data structures like arrays, lists, and databases. Below are common LINQ operations:

---

## **1. Initializing Data**

```csharp
List<int> numbers = new List<int>();
int[] arraye = new int[10];
Array.Fill(arraye, new Random().Next(1, 81));

// Fill numbers list with random values between 1 and 80
for (int i = 0; i < 40; i++)
{
    numbers.Add(new Random().Next(1, 81));
}
```

---

## **2. Filtering Data**

- **`Where`**: Filters elements based on the condition.

```csharp
numbers.Where(x => x % 3 == 0); // Returns an IEnumerable of elements divisible by 3
```

- **`Any`**: Checks if any element matches the condition.

```csharp
numbers.Any(x => x == 17); // Returns true if any element is 17
```

- **`Find`**: Finds the first element that matches the condition.

```csharp
numbers.Find(x => x == 5); // Returns the first element that is 5, or default if not found
```

- **`Distinct`**: Removes duplicates from the collection.

```csharp
numbers.Distinct(); // Returns a list without duplicates
```

- **`DistinctBy`**: Removes duplicates based on a specified key.

```csharp
numbers.DistinctBy(x => x); // Removes duplicates based on the key (property)
```

---

## **3. Ordering and Sorting**

- **`Order`**: Orders the collection in ascending order (deprecated, prefer `OrderBy`).

```csharp
numbers.Order(); // Ascending order
```

- **`OrderBy`**: Orders based on a key (ascending).

```csharp
numbers.OrderBy(x => x); // Orders in ascending order based on the value
```

- **`OrderDescending`**: Orders the collection in descending order (deprecated, prefer `OrderByDescending`).

```csharp
numbers.OrderDescending(); // Descending order
```

- **`OrderByDescending`**: Orders based on a key (descending).

```csharp
numbers.OrderByDescending(x => x); // Orders in descending order based on the value
```

---

## **4. Selection**

- **Convert to List or Array**:

```csharp
arraye.ToList(); // Converts array to List
numbers.ToArray(); // Converts List to Array
```

- **Convert to Dictionary**:

```csharp
int t = 0;
arraye.ToDictionary(x => $"Key {t++}"); // Converts to Dictionary with custom keys
```

---

## **5. Get or Extract Elements**

- **`First`**: Returns the first element.

```csharp
numbers.First(); // Returns the first element of the collection
```

- **`FirstOrDefault`**: Returns the first element, or default if the collection is empty.

```csharp
numbers.FirstOrDefault(); // Returns first element or default value
```

- **`Single`**: Returns the only element in the collection (throws if there’s more than one).

```csharp
numbers.Single(); // Returns the only element, throws if more than one exists
```

- **`SingleOrDefault`**: Returns the only element or default if no elements are found.

```csharp
numbers.SingleOrDefault(); // Returns the only element or default value
```

- **`Last`**: Returns the last element.

```csharp
numbers.Last(); // Returns the last element of the collection
```

- **`LastOrDefault`**: Returns the last element or default if the collection is empty.

```csharp
numbers.LastOrDefault(); // Returns last element or default value
```

---

## **6. Aggregation**

- **`Count`**: Returns the number of elements in the collection.

```csharp
numbers.Count(); // Number of elements in the collection
```

- **`Sum`**: Returns the sum of all elements.

```csharp
numbers.Sum(); // Sum of all elements
```

- **`Average`**: Returns the average of all elements.

```csharp
numbers.Average(); // Average of all elements
```

- **`Max`**: Returns the maximum value in the collection.

```csharp
numbers.Max(); // Maximum value in the collection
```

- **`Min`**: Returns the minimum value in the collection.

```csharp
numbers.Min(); // Minimum value in the collection
```

---

## **7. Pagination**

- **`Take`**: Takes a specified number of elements from the beginning of the collection.

```csharp
numbers.Take(5); // First 5 elements
```

- **`TakeLast`**: Takes a specified number of elements from the end of the collection.

```csharp
numbers.TakeLast(5); // Last 5 elements
```

- **`TakeWhile`**: Takes elements while a condition is true.

```csharp
numbers.TakeWhile(x => x % 3 == 0); // Take elements while divisible by 3
```

- **`Skip`**: Skips a specified number of elements from the beginning of the collection.

```csharp
numbers.Skip(5); // Skip first 5 elements
```

- **`SkipLast`**: Skips a specified number of elements from the end of the collection.

```csharp
numbers.SkipLast(5); // Skip last 5 elements
```

- **`SkipWhile`**: Skips elements while a condition is true.

```csharp
numbers.SkipWhile(x => x % 3 == 0); // Skip elements divisible by 3
```

---

## **Summary**

- **Filtering**: `Where`, `Any`, `Find`, `Distinct`, `DistinctBy`.
- **Ordering**: `OrderBy`, `OrderByDescending`.
- **Selection**: `ToList()`, `ToArray()`, `ToDictionary()`.
- **Get Elements**: `First()`, `Last()`, `Single()`, `FirstOrDefault()`, `LastOrDefault()`.
- **Aggregation**: `Count()`, `Sum()`, `Average()`, `Max()`, `Min()`.
- **Pagination**: `Take()`, `TakeLast()`, `Skip()`, `SkipLast()`, `TakeWhile()`, `SkipWhile()`.

---
