# Design Patterns in Java

This repository demonstrates six design patterns implemented in Java. The design patterns are categorized into three types: Behavioral, Creational, and Structural. Each pattern is presented with its own use case, including real-world examples and corresponding code implementations. The project is structured to adhere to global best practices, including separate files for each class, defensive programming, exception handling, logging, and performance optimization.
## Table of Contents
- [Design Patterns Used](#design-patterns-used)
- [How to Run the Project](#how-to-run-the-project)
- [Design Pattern Implementations](#design-pattern-implementations)
  - [Behavioral Patterns](#behavioral-patterns)
  - [Creational Patterns](#creational-patterns)
  - [Structural Patterns](#structural-patterns)
- [Technologies Used](#technologies-used)
- [Logging and Exception Handling](#logging-and-exception-handling)
- [Project Structure](#project-structure)

---

## Design Patterns Used

This project covers six design patterns:

- **Behavioral Patterns**
  1. Observer Pattern
  2. Command Pattern
- **Creational Patterns**
  3. Singleton Pattern
  4. Factory Pattern
- **Structural Patterns**
  5. Adapter Pattern
  6. Decorator Pattern

---

## How to Run the Project

1. **Clone the repository:**

   ```bash
   git clone https://https://github.com/Bhumil0808/EI_CodingTask.git
   ```

2. **Navigate to the project directory:**

    ```bash
    cd EI_CodingTask/task1EI
    ```

3.  **Compile and run the project using any Java IDE (Eclipse, IntelliJ) or directly from the command line:**

    ```bash
    cd com.behavioral/observerpattern
    javac Main.java
    java main
    ```

Repeat similar steps for other patterns by navigating to their respective folders:

- For Command Pattern: cd com.behavioral/commandpattern
- For Singleton Pattern: cd com.creational/singletonpattern
- For Factory Pattern: cd com.creational/factorypattern
- For Adapter Pattern: cd com.structural/adapterpattern
- For Decorator Pattern: cd com.structural/decoratorpattern

4.  **Run All Tests**
    If you want to execute all patterns, repeat the above steps for each pattern individually.

## Design Pattern Implementations

This section details the six design patterns implemented in the project, categorized into Behavioral, Creational, and Structural patterns.

### Behavioral Patterns

#### 1. **Observer Pattern: Stock Price Notification System**
   - **Description**: The Observer pattern is used when you need to notify multiple objects about changes in the state of another object. In this case, we simulate a stock price notification system, where users (observers) are updated when a stock's price changes.
   - **Example**:
     - `Stock.java`: Represents the subject (stock) whose price can change.
     - `Observer.java`: Interface for observer objects (subscribers).
     - `StockUser.java`: Concrete observer implementation for users.
   - **Key Points**:
     - Allows dynamic registration and removal of observers.
     - Decouples the subject from observers, allowing flexible updates.
   
#### 2. **Command Pattern: Smart Home Remote Control**
   - **Description**: The Command pattern encapsulates a request as an object, allowing parameterization of clients with different requests and queuing operations. In this use case, we simulate a smart home remote control system to turn devices (lights) on and off.
   - **Example**:
     - `Command.java`: Interface for commands.
     - `Light.java`: Receiver class for handling the actual work (turning the light on/off).
     - `LightOnCommand.java` and `LightOffCommand.java`: Concrete command classes to turn the light on and off.
     - `RemoteControl.java`: Invoker class that triggers commands.
   - **Key Points**:
     - Provides flexibility to extend and add new commands without modifying existing code.
     - Decouples the invoker from the actual actions performed by the receiver.

### Creational Patterns

#### 3. **Singleton Pattern: Database Connection Manager**
   - **Description**: The Singleton pattern ensures a class has only one instance and provides a global point of access to it. In this use case, the pattern is used to manage a database connection where only a single connection instance is allowed.
   - **Example**:
     - `DatabaseConnection.java`: A singleton class that restricts the instantiation of a database connection.
   - **Key Points**:
     - Guarantees that only one instance is created, minimizing resource usage for database connections.
     - Thread-safe implementation ensures proper behavior in multi-threaded environments.

#### 4. **Factory Pattern: Shape Factory**
   - **Description**: The Factory pattern is used to create objects without exposing the creation logic to the client. It provides a way to delegate the instantiation process to subclasses. This example demonstrates the creation of different shapes (Circle, Square) based on user input.
   - **Example**:
     - `Shape.java`: Abstract interface for shapes.
     - `Circle.java`, `Square.java`: Concrete classes that implement the `Shape` interface.
     - `ShapeFactory.java`: Factory class responsible for creating the shape objects.
   - **Key Points**:
     - The Factory pattern allows for more flexibility by enabling polymorphism and adhering to the Open/Closed Principle.
     - Helps manage object creation without the need to modify client code when adding new shapes.

### Structural Patterns

#### 5. **Adapter Pattern: Mobile Phone Charger**
   - **Description**: The Adapter pattern converts one interface into another that the client expects. In this use case, the adapter allows a European charger to work in a system that only accepts standard chargers.
   - **Example**:
     - `Charger.java`: The target interface expected by the system.
     - `EuropeanCharger.java`: Adaptee class that needs adaptation.
     - `ChargerAdapter.java`: Adapter class that bridges the European charger with the expected system interface.
   - **Key Points**:
     - Provides an interface compatibility solution without modifying the existing classes.
     - Useful for integrating new components into existing systems without rewriting the code.

#### 6. **Decorator Pattern: Text Editor with Spell Check**
   - **Description**: The Decorator pattern adds functionality to an object dynamically without altering its structure. In this use case, a text editor adds spell check functionality via a decorator.
   - **Example**:
     - `TextEditor.java`: Component interface representing the core text editor.
     - `BasicTextEditor.java`: Concrete implementation of the text editor.
     - `SpellCheckDecorator.java`: Decorator class that adds spell-check functionality to the basic editor.
   - **Key Points**:
     - The pattern enables the dynamic addition of responsibilities to objects, adhering to the Open/Closed Principle.
     - Provides flexibility in extending object functionalities without inheritance.

---

## Technologies Used

This project utilizes the following technologies:

- **Java**: The core programming language for implementing all design patterns. Java is known for its rich set of libraries and frameworks, making it a suitable choice for implementing design patterns.
- **Java Standard Library (JDK 11)**: Provides various built-in classes and interfaces that help implement the design patterns effectively.
- **Logging Framework**: Java's `java.util.logging.Logger` is used for structured logging, capturing important events and aiding in debugging.

---

## Logging and Exception Handling

To ensure the robustness of the code, extensive logging and exception handling mechanisms have been implemented:

### Logging

- The `java.util.logging.Logger` class is used across the project to capture significant events. For instance:
  - **Class Instantiations**: When an object is created, a log entry records this event.
  - **Method Calls**: Each method call that impacts system state (e.g., executing a command, notifying observers) is logged.
  - **Execution Flow**: Key parts of the code, such as database connection setup and factory method invocation, are logged for debugging purposes.
  
## Project Structure
**The below is the Structure of Project**
   ```bash
task1EI/
├── behavioral/
│   ├── observer/
│   │   ├── Stock.java
│   │   ├── Observer.java
│   │   ├── StockUser.java
│   │   ├── Main.java
│   └── command/
│       ├── Command.java
│       ├── Light.java
│       ├── LightOnCommand.java
│       ├── LightOffCommand.java
│       ├── RemoteControl.java
│       ├── Main.java
├── creational/
│   ├── singleton/
│   │   └── DatabaseConnection.java
│   │   └── Main.java
│   ├── factory/
│       ├── Shape.java
│       ├── Circle.java
│       ├── Square.java
│       └── ShapeFactory.java
│       └── Main.java
├── structural/
│   ├── adapter/
│   │   ├── Charger.java
│   │   ├── EuropeanCharger.java
│   │   └── ChargerAdapter.java
│   │   └── Main.java
│   └── decorator/
│       ├── TextEditor.java
│       ├── BasicTextEditor.java
│       └── SpellCheckDecorator.java
│       └── Main.java
|

```
