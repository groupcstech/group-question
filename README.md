
Frieadam fenta  uur02093/16.  

 Natnael guta   uur01662/16
 
we weren't class because we had special class mid test,and we did the assignment.
# WINDOW PROGRAMMING – GROUP ASSIGNMENT

## PART 1: SOFTWARE DEVELOPMENT, METHODOLOGIES AND PRINCIPLES (CHAPTER 1)

### Question 1: Choosing the Right SDLC Model

**Selected Scenario: A – Flight-control software for a commercial aircraft**

**Answer:**

The best SDLC model for developing aircraft flight-control software is the **Spiral Model** because it focuses on risk analysis, reliability, and continuous testing. Aircraft software is safety-critical, and even a small error can cause serious accidents.

**Reasons:**

1. **Requirements Stability:** Requirements are mostly fixed and must follow strict aviation standards.
2. **Risk Tolerance:** Risk tolerance is very low because human lives depend on the system.
3. **Project Complexity:** The software is large and complex, requiring careful development.
4. **Testing:** Testing is performed in every development cycle to identify and correct errors early.

**Comparison with Other Models:**
- **Waterfall:** Provides a structured process but is less flexible when problems are discovered.
- **Agile/Scrum:** Supports changing requirements but is less suitable as the main approach for highly regulated aircraft software.
- **RAD:** Focuses on fast development, while aircraft software requires extensive safety testing.

**Conclusion:** The Spiral Model is the best choice because it emphasizes risk management, reliability, and continuous testing rather than development speed.

---

### Question 2: The Hidden Trade-offs of Rapid Application Development (RAD)

**Answer:**

RAD is a software development model that focuses on rapid prototyping, user feedback, and fast delivery instead of extensive upfront planning.

However, skipping detailed planning can create several problems:

1. **Architectural Debt:** Quick design decisions can make future maintenance difficult.
2. **Scalability Problems:** Software designed for a small number of users may fail when the number increases.
3. **Reliability Problems:** Insufficient testing can leave hidden errors in the system.
4. **Security Risks:** Lack of detailed planning may cause developers to overlook security weaknesses.
5. **Poor Risk Analysis:** Technical problems may not be identified early.

**Example:**

A banking application developed quickly using RAD may work for 100 users but become slow or fail when thousands of users access it simultaneously because its architecture was not properly planned.

**Conclusion:** RAD is suitable for small and medium-sized projects requiring fast delivery. However, it is less suitable for large-scale or mission-critical systems because insufficient planning can cause scalability and reliability problems.

---

### Question 3: Balancing Software Development Principles

**Answer:**

DRY, KISS, YAGNI, and Separation of Concerns are important software development principles.

1. **DRY (Don't Repeat Yourself):** Avoids unnecessary code duplication by using reusable methods and classes.
2. **KISS (Keep It Simple, Stupid):** Encourages simple designs and avoids unnecessary complexity.
3. **YAGNI (You Aren't Gonna Need It):** Avoids developing features that are not currently required.
4. **Separation of Concerns:** Divides a program into different parts, each handling a specific responsibility.

**Can DRY and Separation of Concerns violate KISS or YAGNI?**

Yes. Applying them too aggressively can create unnecessary classes, interfaces, and layers, making a simple program complicated.

**Example:**

For a simple calculator, creating multiple abstract classes, interfaces, and service layers for basic addition and subtraction is over-engineering. A single Calculator class with two methods is enough.

**Conclusion:** Developers should balance these principles and choose the simplest design that satisfies the current requirements without unnecessary complexity.

---

### Question 4: The Economics of Testing and Code Quality

**Answer:**

The cost of correcting software errors is lowest during the early stages of development and highest after deployment because later errors may affect many parts of the system and its users.

**Stages of Error Correction:**

1. **Requirements and Design:** Errors are cheap to fix because coding has not started.
2. **Coding:** Errors can be corrected by modifying the affected code.
3. **Testing:** Fixing errors may require repeating tests and checking other components.
4. **After Deployment:** Errors are expensive because they may affect users, data, and business operations.

**How modern practices reduce costs:**

- **TDD (Test-Driven Development):** Developers write tests before writing code, helping identify errors early. It follows Red, Green, and Refactor.
- **Continuous Integration (CI):** Frequently combines code changes and automatically tests them to detect problems early.
- **Peer Code Reviews:** Other developers examine code to identify mistakes, security problems, and poor coding practices.

**Conclusion:** Early testing and code reviews reduce the cost of fixing errors, improve software quality, and prevent defects from reaching users.

---

# PART 2: .NET ARCHITECTURE, C# AND WINDOW PROGRAMMING (CHAPTER 2)

### Question 5: MSIL, JIT, and Platform Independence

**Answer:**

In .NET, source code written in C# or VB.NET is compiled into Microsoft Intermediate Language (MSIL), which is independent of a specific CPU.

**Compilation Process:**

1. Developers write source code.
2. The compiler converts it into MSIL.
3. The JIT (Just-In-Time) compiler converts MSIL into native machine code.
4. The processor executes the machine code.

**Why are traditional .NET Framework applications platform-dependent?**

Although MSIL is CPU-independent, traditional .NET Framework applications depend on the Windows CLR and Windows-specific libraries and APIs.

For example, Windows Forms applications use Windows-specific graphical components.

**How did Mono change this?**

Mono provides a .NET-compatible runtime that allows supported .NET applications to run on operating systems such as Linux and macOS.

**Difference:**
- **CPU Independence:** MSIL can be converted into machine code for different processors.
- **OS Independence:** Applications can run on different operating systems when compatible runtimes and libraries are available.

**Conclusion:** MSIL provides CPU independence, but operating-system independence also requires compatible runtimes and libraries. Mono helped extend .NET applications beyond Windows.

---

### Question 6: Managed vs. Unmanaged Code and Language Interoperability

**Answer:**

**Managed Code** runs under the control of the Common Language Runtime (CLR), while **Unmanaged Code** runs outside the CLR.

**1. Managed Code**

The CLR provides important services:

- **Garbage Collection:** Automatically manages unused memory.
- **Type Safety:** Prevents invalid operations between incompatible types.
- **Metadata:** Stores information about classes, methods, and types.
- **Array Bounds Checking:** Prevents accessing invalid array positions.
- **Exception Handling:** Helps manage runtime errors.

**2. Unmanaged Code**

Unmanaged code runs outside the CLR and requires more direct resource management. It may suffer from memory leaks, invalid memory access, and buffer overflows.

**3. Role of MSIL**

MSIL allows different .NET languages, such as C# and VB.NET, to compile into a common intermediate language and work together.

**4. Role of CTS (Common Type System)**

CTS ensures that different .NET languages use compatible data types.

For example, C# `string` and VB.NET `String` both represent `System.String`.

**Conclusion:** Managed code improves safety through CLR services, while MSIL and CTS allow C# and VB.NET components to communicate and share compatible data types.

---

### Question 7: Solving DLL Hell – Assemblies, Manifests, and Namespaces

**Answer:**

DLL Hell occurs when installing one application replaces a shared DLL with an incompatible version, causing another application to fail.

.NET reduces this problem through the following features:

1. **Assemblies:** Basic units of deployment and versioning in .NET. They contain compiled code and metadata.
2. **Manifest:** Contains assembly information such as its name, version, and dependencies.
3. **Strong Names:** Uniquely identify assemblies using their name, version, culture, and public key.
4. **Global Assembly Cache (GAC):** Stores shared .NET Framework assemblies and supports different versions.
5. **Private Assemblies:** Stored in an application's directory and used by that application.
6. **Shared Assemblies:** Designed to be used by multiple applications.

**Difference Between Namespace and Assembly:**

- **Namespace:** A logical grouping of related classes and types.
- **Assembly:** A physical deployment unit containing compiled code and metadata.

For example, `System.Collections` is a namespace, while a DLL file is an assembly.

**Conclusion:** Assemblies, manifests, strong names, and the GAC help prevent DLL version conflicts. Namespaces organize code logically, while assemblies organize code physically.

---

### Question 8: Abstraction in Data Access – ADO.NET vs. Entity Framework and LINQ

**Answer:**

.NET provides ADO.NET, Entity Framework, and LINQ for accessing and managing data.

**1. ADO.NET**

ADO.NET provides direct database access using connections, commands, DataReaders, and DataSets.

Developers must manually manage connections, write SQL queries, retrieve data, and handle errors.

**2. Why Are Manual Connections and DataSets Error-Prone?**

- Developers may forget to close database connections.
- Manual SQL queries can contain errors.
- Data conversion requires extra work.
- Repeated code makes maintenance difficult.

**3. Entity Framework (EF)**

Entity Framework is an Object-Relational Mapping (ORM) framework that converts database tables into .NET objects.

For example, a `Students` database table can be represented by a C# `Student` class.

**Benefits:**
- Reduces repetitive code.
- Simplifies database operations.
- Improves maintainability.
- Reduces manual data conversion.

**Trade-off:** It may introduce performance overhead and provide less direct control over SQL queries.

**4. LINQ (Language Integrated Query)**

LINQ allows developers to query different data sources using a consistent syntax, including SQL databases, XML, and collections.

Example:

```csharp
int[] numbers = { 10, 20, 30, 40, 50 };

var result = from n in numbers
             where n > 20
             select n;
```

This selects numbers greater than 20.

**Conclusion:** ADO.NET provides direct database control, Entity Framework simplifies database operations through objects, and LINQ provides a common way to query different data sources.

---

# PART 3: EVENT-DRIVEN PROGRAMMING

### Question 9: Under the Hood of Event-Driven Programming

**Answer:**

A Console application executes instructions sequentially from the `Main()` method, while a Windows Forms application uses event-driven programming and waits for user actions.

**What Happens When a User Clicks a Button?**

1. The user clicks a button.
2. Windows generates a message for the mouse action.
3. The message enters the application's message queue.
4. The message loop retrieves and processes it.
5. The application raises the button's Click event.
6. The registered event handler executes.
7. The application performs the required action.
8. The program returns to the message loop and waits for another event.

**Example:**

```csharp
private void button1_Click(object sender, EventArgs e)
{
    MessageBox.Show("Button Clicked!");
}
```

This code displays a message when the user clicks the button.

**Difference Between Console and Windows Forms:**

| Console Application | Windows Forms |
|---|---|
| Sequential execution | Event-driven execution |
| Uses console input | Uses graphical controls |
| Executes until completion | Waits for user events |
| Normally has no GUI message loop | Uses a message loop |

**Conclusion:** Windows Forms uses event-driven programming to respond to user actions. The message loop processes events and executes the appropriate event handlers, making applications interactive.
