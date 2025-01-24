# Object-Oriented Programming (OOP) Principles and Definitions

## **1. Define Scope**

**Scope**: A set of objects that interact with each other using specific operations for each type of object. Each object has unique properties to describe its characteristics.

---

## **2. Define The Mandatory Object**

**Mandatory Objects (أركان النظام الأساسية)**: These are essential components for a system to function, without which the system cannot operate.

---

## **3. Determine The Software Type**

- **A**: Customized Software
- **B**: Generalized Software

---

## **4. Object-Oriented Programming (OOP) Principles**

### **1. Abstraction (التجريد)**

**Definition**: Present an object or component in its simplest form, hiding unnecessary details.

- **Summarize Objects**: Create a general template (class) that encompasses a collection of objects.
  - **Example Classes**:
    - Admin, Employee, Car, Client, Contract, Insurance, Invoices, Rating
- **Define Properties for Each Class**:
  - **Admin**: Name, Email, Password
  - **Client**: (Define properties based on system requirements)
  - **Employee**: Name, Email, Password, Phone, NationalId, Signature, Position, Permission
  - **Car**: PlateNo, Brand, Model, MY, Color
  - **Contract**: StartDate, EndDate
  - **Insurance**: Type, Amount, Description, StartDate, EndDate
  - **Invoice**: Amount, Tax, Discount
  - **Rating**: Comment, StarAmount

### **2. Behavior of Objects**

- **Actors (Human users and systems)**:

  - Actors typically make changes to the system (99% human, 1% AI/system).

- **Object (Car, Contract, Insurance, Invoice, Rating)**: Define behavior for each class based on interactions with the actors.

- **Operations**:
  - Determine operations for each actor, class, and service.
  - Define return data type, operation name, and inputs for each operation.

---

### **3. Generalization & Specialization (Restructuring)**

**Generalization**: Extract common features from multiple objects into a generalized class.

**Specialization**: Create more specific classes that inherit from generalized classes, adding specialized features.

---

## **4. Key OOP Concepts**

### **1. Inheritance**

- **Relationship Between Classes**: Defines how one class (child) inherits properties and behaviors from another (parent).
  - **Types**:
    - **Association**: One-to-one, one-to-many, many-to-many relationships between objects.
    - **Composition**: The parent object owns or contains child objects.
    - **Aggregation**: A weaker form of composition, where child objects can exist independently.

### **2. Polymorphism**

- **Definition**: The ability for different objects to respond to the same message (method) in different ways.
  - **Types**:
    - **Method Overloading**: Same method name but different parameters.
    - **Method Overriding**: Redefining a method in a subclass to provide a new implementation.

### **3. Encapsulation**

- **Definition**: Control access to the components of a class, restricting direct access to its internal state and providing controlled access through methods (getters and setters).
- **Access Levels**:
  - **Public**: Accessible from any other class.
  - **Private**: Accessible only within the class.
  - **Protected**: Accessible within the class and by subclasses.
  - **Internal**: Accessible only within the same assembly.

---

## **5. Example System Breakdown**

### **Actors and Operations**:

- **Actors**: Admin, Employee, Client, System
- **Classes**: Car, Contract, Insurance, Invoice, Rating

### **Operations for Each Class**:

- **Car Class Operations**:
  - StartEngine(), StopEngine(), GetFuelLevel()
- **Invoice Class Operations**:
  - GenerateInvoice(), ApplyDiscount(), CalculateTax()
- **Contract Class Operations**:
  - RenewContract(), CalculateDuration()

---

By following these principles and definitions, you can structure and build an object-oriented system where each component (object) has its own properties, behaviors, and interactions with other objects. The use of abstraction, inheritance, polymorphism, and encapsulation helps achieve maintainability, scalability, and flexibility in software design.
