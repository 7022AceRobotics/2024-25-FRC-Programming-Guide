## FRC 2025 Java Style Guide
Practices to follow to ensure consistency, readable and maintainability. If you're going to take at least
one thing from this guide, please let it be the naming conventions and documentation. Please follow these guidelines.

Furthermore, you're working in a team environment. **Document your code.** Be mindful.

## Table of Contents
1. [Naming Conventions](#naming-conventions)
   - [Functions](#functions)
   - [Variables](#variables)
   - [Files](#files)
2. [Formatting](#formatting)
   - [Tabs or Spaces](#tabs-or-spaces)
   - [Line Length](#line-length)
3. [Commenting](#commenting)
   - [Class Documentation](#class-documentation)
   - [Variable Documentation](#variable-documentation)
   - [Function Definition Documentation](#function-definition-documentation)
4. [Practices](#practices)
   - [Java @Override](#java-override)
   - [Catching Exceptions](#catching-exceptions)
   - [Static Members](#static-members)
   - [Public, Protected, and Private Methods](#public-protected-and-private-methods)
5. [Scoping](#scoping)
   - [Local Variables](#local-variables)
   - [Global Variables](#global-variables)
   - [Constants](#constants)

## Naming Conventions

### Functions
- Functions and methods must be named using **camelCase**.
- This convention should be applied consistently for all methods/functions in the code.
  
Example:

```java
/*
    Good function naming convention.
    camelCase.
*/
void myFunctionForFRC() {}

/*
    Bad function naming convention.
    Other naming conventions like snake_case, PascalCase.
*/
void BadFunctionNaming1() {}
void bad_function_naming_2() {}
```

### Variables
- Variables must be named using camelCase.
- Ensures readability and consistancy.

Example:
```java
void foo() {
    boolean isFalse = false;
    boolean isTrue = true;
}
```

## Files
- File names must be written using PascalCase.
- This applies to all classes, interfaces, and important utility files.

**Example directory structure:**
```
Source
   Main.java
   Robot.java
   Utils
      RobotUtilities.java
      GrabSystem.java
```

## Formatting
### Tabs or Spaces
- Tabs should be used for indentation (4 spaces per tab).
- Spaces can be used inside methods if alignment is required, but only for the purpose of clarity.

### Line Length
- There is no set maximum line length, but strive to keep lines under 120 characters for readability.

## Commenting
### Class Documentation
- Every class should have a header comment that explains its purpose, usage, and any relevant details.

Example:
```java
/**
 * This class controls the robot's driving system.
 * It manages forward and turning movements based on input from sensors.
 */
public class DriveSystem {
    // Implementation...
}
```

### Variable Documentation
- Variables should only be documented if their purpose is not immediately obvious.
- Use the following format for documenting variables:

```java
// speed: The speed of the robot in meters per second.
private double speed;
```

### Function Definition Documentation
- Every function should have a docstring explaining its purpose, parameters, and return values.

Example:
```java
/**
 * This function drives the robot forward.
 * 
 * @param distance The distance to drive in meters.
 * @return boolean True if the robot successfully reached the destination, false otherwise.
 */
public boolean driveForward(double distance) {
    // Implementation here
}
```

## Practices
### Java @Override
- Always use the @Override annotation when overriding methods in a subclass.

Example:

```java
@Override
public void robotInit() {
    // Initialization code here
}
```

### Catching Exceptions
- Always catch specific exceptions (not just Exception).
- When catching exceptions, provide meaningful logging or recovery behavior.

Example:

```java
try {
    // risky operation
} catch (IOException e) {
    System.out.println("File error: " + e.getMessage());
}
```

### Static Members
- Use static members only when they do not rely on instance-specific data.
- Avoid static members unless necessary for utility purposes (e.g., constants, helper methods).

### Public, Protected, and Private Methods
- Use private for internal methods that should not be accessed outside the class.
- Use protected for methods that should be available to subclasses.
- Public methods should be used sparingly. Only expose methods that are needed by other parts of the program.

Example:
```java
public class Robot {
    // Public method accessible outside the class
    public void moveForward() {
        // Implementation here
    }

    // Private method used only inside this class
    private void resetMotors() {
        // Implementation here
    }
}
```

## Scoping
### Local Variables
- Avoid storing return values from functions into local variables unless necessary.
- The use of local variables is discouraged unless they are essential for calculations or short-lived purposes.

### Global Variables
- Global variables should be used sparingly, as they can lead to tight coupling and make testing more difficult.
- Always prefer encapsulating data within classes and objects.

### Constants
- Constants should be defined using ALL_CAPS and static final.

Example:
```java
public class Robot {
    public static final double MAX_SPEED = 12.5;  // Maximum speed in meters per second
}
```
