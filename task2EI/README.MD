# Smart Home System Simulation

This repository demonstrates a simulation for controlling smart devices (e.g., lights, thermostats, and door locks) via a central hub in a Smart Home System. The project is designed with best practices, including **Object-Oriented Programming (OOP)** principles, **SOLID** principles, and design patterns like **Factory**, **Observer**, and **Command**. This simulation allows easy automation, control, and extension of smart devices.

## Table of Contents

- [Design Patterns Used](#design-patterns-used)
- [How to Run the Project](#how-to-run-the-project)
- [Project Structure](#project-structure)
- [Design Pattern Implementations](#design-pattern-implementations)
  - [Factory Pattern](#factory-pattern)
  - [Observer Pattern](#observer-pattern)
  - [Command Pattern](#command-pattern)
- [Technologies Used](#technologies-used)
- [Logging and Exception Handling](#logging-and-exception-handling)

---

## Design Patterns Used

This project utilizes multiple design patterns to provide a flexible and scalable system:

- **Factory Pattern**: To create various smart devices (like lights, thermostats, door locks) dynamically.
- **Observer Pattern**: To implement automation where devices can react to changes from the central hub (e.g., switching on the lights when a door is unlocked).
- **Command Pattern**: To encapsulate device commands (turn on/off) and trigger them via remote control.

---

## How to Run the Project

1. **Clone the repository:**

    ```bash
    git clone https://github.com/bhumil0808/EI_CodingTask.git
    ```

2. **Navigate to the project directory:**

    ```bash
    cd EL_CodingTask/task2EI
    ```

3. **Compile and run the project using a Java IDE (e.g., Eclipse, IntelliJ) or directly from the command line:**

    ```bash
    javac Main.java
    java Main
    ```

    This will start the simulation and allow interaction with the Smart Home System.

---

## Project Structure

The project is structured to follow a clean architecture, and the design pattern implementations are separated into different packages.

```bash
task2EI/
├──Device.java           
├──Light.java            
├──Thermostat.java       
├──DoorLock.java         
├──DeviceFactory.java
├──HomeHub.java
├──Trigger.java
└──Main.java     
```            


## Design Pattern Implementations

### Factory Pattern

#### Device Creation Using Factory

- **Description**: The Factory pattern is used to create various smart devices without specifying the exact class of the object that will be created. This allows for easy addition of new devices in the future.

- **Key Classes**:
  - `DeviceFactory.java`: A factory class that handles the instantiation of smart devices.
  - `Device.java`: An interface for all smart devices.
  - `Light.java`, `Thermostat.java`, `DoorLock.java`: Concrete classes representing different smart devices.

### Observer Pattern

#### Automation System Using Observer

- **Description**: The Observer pattern is used to notify devices of changes in the central hub. Devices "observe" the hub and respond when the hub's state changes.

- **Key Classes**:
  - `HomeHub.java`: Represents the central hub (subject) that manages devices and triggers.
  - `Trigger.java`: Class that defines the condition and action for automation.

- **Real-World Use Case**:
  - Lights turn on automatically when the front door is unlocked.
  - Thermostat adjusts the temperature when someone enters the home.

### Command Pattern

#### Remote Control System Using Command

- **Description**: The Command pattern encapsulates device commands such as turning on and off. Commands can be triggered via the central hub.

- **Key Classes**:
  - `Command.java`: Interface for all commands (like turning devices on/off).
  - `RemoteControl.java`: Invoker that calls the commands to control the devices.

- **Real-World Use Case**:
  - Using the central hub to turn on/off smart lights, thermostat, or locks.

## Classes Overview

- `Device`: Interface for all smart devices, providing methods to get device ID, type, status, and control methods (`turnOn`, `turnOff`).
- `DeviceFactory`: Factory class for creating smart devices.
- `Light`: Concrete class representing a light device.
- `Thermostat`: Concrete class representing a thermostat device.
- `DoorLock`: Concrete class representing a door lock device.
- `HomeHub`: Central hub class managing devices and triggers.
- `Trigger`: Class for defining conditions and actions for automation.

## Usage

1. **Add Devices**: Use `DeviceFactory` to create devices and add them to the `HomeHub`.
2. **Control Devices**: Turn devices on/off using the `HomeHub`.
3. **Set Triggers**: Define automation rules with conditions and actions.
4. **Check Status**: Retrieve the status of all devices.

---

## Technologies Used

The following technologies are used in this project:

- **Java (JDK 11)**: Core programming language for implementing the simulation and design patterns.
- **Logging Framework**: Java’s `java.util.logging` for capturing important events like device status changes, hub actions, and error handling.

---

## Logging and Exception Handling

### Logging

- **Logging Framework**: The `java.util.logging.Logger` is used throughout the project for structured logging.
  - **Class Instantiations**: Logs when devices or commands are created.
  - **Method Calls**: Logs important method calls like device on/off commands, hub state changes, and automation triggers.

### Exception Handling

- Defensive programming techniques have been applied to prevent unexpected failures.
- Custom exceptions are thrown where necessary, such as invalid device creation in the factory or command execution errors.