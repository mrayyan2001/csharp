# 1. Abstraction (التجريد)

## a. Summarize the Objects (ايجاد قالب عام يضم او يوصف مجموعه من الكائنات)

Abstraction involves simplifying a system by summarizing its components into general templates (classes).

### **1. Represent the System Objects Using Templates (Classes)**

- **Admin**: Name, Email, Password
- **Client**
- **Employee**: Name, Email, Password, Phone, NationalId, Signature, Position, Permission
- **Car**: Plate No, Brand, Model, Manufacturing Year, Color
- **Contract**: Start Date, End Date
- **Insurance**: Type, Amount, Description, Start Date, End Date
- **Invoice**: Amount, Tax, Discount
- **Rating**: Comment, Star Rating

### **2. Define Properties for Each Template (Class)**

Each class should define its properties for easy abstraction and management of system components.

## b. Define the Object Behavior

Objects have behavior (methods), and their behavior must be clearly defined.

### **1. Actor**

Actors are the active users who make changes to the system.

- **Human (99%)**: Most changes are made by human users.
- **AI/System (1%)**: Some system processes can be automated.

### **2. Objects**

- Car
- Contract
- Insurance
- Invoice
- Rating

### **3. Lookup**

- Admin manages multiple Employees, Cars, and Contracts.
- For each contract, Admin can manage Insurance, Invoices, and Ratings.

### **Determine the Operations**:

- **For Each Actor**: Identify all possible operations each actor can perform.
- **For Each Class**: Identify CRUD (Create, Read, Update, Delete) operations for each class.
- **For Each Service**: Define operations for services such as Rental Requests, Signing Contracts, Ending Rentals, etc.

---

## c. Generalization & Specialization (Restructuring)

### **1. Inheritance**

- **Relationships Between Classes**: Use association, inheritance, and composition/aggregation to determine how classes relate.

### **2. Polymorphism**

- **Implementation**: Implement polymorphism using method overloading and overriding to allow different behaviors for the same method.

### **3. Encapsulation**

- Manage access to class components by defining appropriate access levels for properties and methods.

### **Abstract Methods**

Abstract methods define the structure of a method without providing an implementation.

- Abstract methods should be available in abstract classes and interfaces.
- Abstract methods must be overridden in subclasses to provide the implementation.

---

## 2. Abstract Classes vs. Interfaces

### **1. Abstract Class**

An abstract class defines a base class that cannot be instantiated. It may contain both abstract methods (without implementation) and implemented methods.

- **Cannot be instantiated**.
- **Abstract methods** must be declared with the `abstract` keyword.
- **Cannot define private abstract methods**.

### **2. Interface**

An interface defines a contract that classes can implement. It cannot contain implementation, only method signatures.

- **Cannot be instantiated**.
- **Methods are abstract by default**, no need for the `abstract` keyword.
- **Supports multiple inheritance** (classes can implement multiple interfaces).
- **Cannot store fields**, only methods, properties, and comments.
- **Default access modifier** is `public`.

### **Differences**:

- **Abstract Class**: Can have both abstract and implemented methods. Suitable for shared behavior.
- **Interface**: Can only define method signatures. Multiple interfaces can be implemented, but they cannot store fields.

---

## 3. Access Modifiers

Access modifiers control the visibility and accessibility of members in a class or interface.

- **Private**: Accessible only within the class or file. Default for class members (fields/properties/methods).
- **Internal**: Accessible only within the same namespace.
- **Public**: Accessible across multiple namespaces.
- **Protected**: Accessible within the class and derived classes.

### Method Access Modifiers:

- The method access modifier must be **equal to or less restrictive** than the class's access modifier.

---

## 4. Async/Await and Operation Management

### **Make Operations Awaitable**:

- **Async/Await**: Ensure all operations are asynchronous and use the `async`/`await` keywords to prevent blocking.
- **Task<>**: Return `Task<>` for asynchronous methods, allowing for proper asynchronous execution.

### **Default Properties for Classes**:

Each class should have the following default properties:

- **Id**: Unique identifier for each instance of the class.
- **CreationDate**: When the object was created.
- **CreatedBy**: Who created the object.
- **UpdateDate**: When the object was last updated.
- **UpdatedBy**: Who last updated the object.
- **IsDeleted**: Boolean flag indicating if the object is deleted or active.

### **Shared Class for Common Properties**:

Create a shared class (e.g., `Entity`, `MainEntity`, `ParentEntity`) to hold these common properties.

---

## 5. Inheritance and Code Structure

### **Inheritance in C#**:

- C# does **not support multiple inheritance** (a class cannot inherit from more than one class).
- Use **generalized parent classes** to share common behavior and properties.

### **Parent Class Access Modifier**:

- The access modifier of the parent class must be the same or **more permissive** than the child class.

---

## 6. OOP Approach

### **File Structure**:

Organize your solution with the following folders:

- **Shared Helpers**: Common helpers, generics, and extensions.
- **Custom Entities**: Core system entities like classes, interfaces, and services.
  - **Entities**: Represent system components (object templates).
  - **Contract**: Defines blueprints for provided services (abstract methods).
  - **Service**: Holds the implementation for real services.

### **Steps for Implementing OOP**:

1. **Entities Folder**: Add system classes here.
2. **Class Properties**: Define properties for each class in the Entities folder.
3. **Class Implementation**: Divide classes into actors and objects. Establish relationships.
4. **Operations**:
   - List operations for each **actor**.
   - Identify CRUD operations for each **class**.
   - Categorize operations for each **service**.

---

## 7. Generalization & Specialization

### **For Classes (Generalization)**:

- Examine all classes and identify similar properties.
- Bring all shared properties together (e.g., datatype, name, usage, scope, constraints).

### **For Interfaces (Specialization)**:

- Identify methods with the same input, name, and return datatype and bring them into shared interfaces.

---

## Conclusion

This design ensures:

1. **Separation of Concerns**: Classes focus on specific responsibilities (abstraction).
2. **Code Reusability**: By using inheritance and interfaces, we can reduce duplication.
3. **Maintainability**: By ensuring all operations are async/await and removing tightly coupled components, we improve scalability and maintenance.

---
