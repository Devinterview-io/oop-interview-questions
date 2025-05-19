# 52 Important OOP Interview Questions in 2025

<div>
<p align="center">
<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

#### You can also find all 52 answers here 👉 [Devinterview.io - OOP](https://devinterview.io/questions/web-and-mobile-development/oop-interview-questions)

<br>

## 1. What is _Object-Oriented Programming (OOP)_?

**Object-Oriented Programming** is a programming paradigm that organizes code into **self-contained objects**. 

Each object combines data and the methods that operate on that data, resulting in more modular, flexible, and reusable code.

### Core Concepts

#### Classes and Objects

A **class** serves as a blueprint for creating objects, defining their attributes and methods.

An **object** represents an instance of a class. It contains both data (attributes of the class) and the methods designed to manipulate that data.

#### Encapsulation

**Encapsulation** refers to the bundling of data and related methods within a class, keeping them hidden to protect their integrity.

External code accesses them through public methods, often referred to as **getters** (to read the attributes) and **setters** (to change them).

#### Inheritance

**Inheritance** allows for the creation of new classes that inherit properties and methods of existing classes. It promotes code reuse and establishes a hierarchical relationship.

The class being inherited from is the **base class** or **superclass**, while the class inheriting is the **derived class** or **subclass**.

#### Polymorphism

**Polymorphism** allows objects of **derived classes** (subclasses) to be treated as objects of their **base class** (the superclass) but still maintain their unique behaviors.

This enables objects to respond uniquely to the same method call, especially when various classes share a method name but have differing implementations.

- **Compile-Time Polymorphism**: Determined before the code runs, typically using method overloading.
- **Run-Time Polymorphism**: Determined while the code is running, typically through method overriding.

#### Abstraction

**Abstraction** is all about creating a simple interface that exposes only relevant and necessary functionalities.

- **Abstract Classes**: Generalized classes, therefore not instantiated directly. They serve as base classes for derived ones.
- **Interfaces**: Set guidelines for classes, specifying which methods they must implement.

#### Associations

Objects often have relationships with other objects, such as one object using or being composed of others. Such relationships are defined as **associations**.

- **Aggregation**: One object owns or contains the other, indicated by a "has-a" relationship.
- **Composition**: A stronger form of aggregation, where the child cannot exist without the parent.

### Benefits of OOP

- **Modularity**: Objects are organized into standalone entities and communicate through public interfaces, promoting code separation and easier maintenance.
- **Reusability**: Objects and class hierarchies can be reused in different projects. Additionally, inheritance allows classes to acquire attributes and behaviors from parent classes.
- **Extensibility**: New features can be incorporated through class inheritance and interface implementation.
- **Flexibility**: Polymorphism enables objects to adapt their behavior based on context.

### Code Example: OOP

Here is the Java code:

```java
// Abstract base class
abstract class Animal {
    private String name;

    public Animal(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    // Abstract method
    public abstract void makeSound();

    public void sleep() {
        System.out.println(name + " is sleeping.");
    }
}

// Derived class
class Lion extends Animal {
    public Lion(String name) {
        super(name);
    }

    @Override
    public void makeSound() {
        System.out.println("Roar!");
    }
}

// Derived class
class Parrot extends Animal {
    private String color;

    public Parrot(String name, String color) {
        super(name);
        this.color = color;
    }

    public String getColor() {
        return color;
    }

    @Override
    public void makeSound() {
        System.out.println("Squawk!");
    }
}

public class Zoo {
    public static void main(String[] args) {
        Lion simba = new Lion("Simba");
        Parrot rio = new Parrot("Rio", "Blue");

        System.out.println(simba.getName() + " is a Lion.");
        simba.makeSound();
        simba.sleep();

        System.out.println(rio.getName() + " is a " + rio.getColor() + " Parrot.");
        rio.makeSound();
        rio.sleep();
    }
}
```

In the example:
- **Classes and Objects**: `Animal` is a class, while `simba` and `rio` are objects.
- **Encapsulation**: Animal's `name` attribute and Parrot's `color` attribute are encapsulated with private visibility, and public getter methods are provided.
- **Inheritance**: Both `Lion` and `Parrot` classes inherit from the `Animal` class.
- **Polymorphism**: Both `Lion` and `Parrot` provide their own implementation of the `makeSound()` method, even though they are treated as `Animal` objects.
- **Abstraction**: The `Animal` class contains the abstract method `makeSound()`, ensuring derived classes provide their own implementation.
<br>

## 2. What is the difference between _procedural_ and _Object-Oriented_ programming?

**Procedural** and **Object-Oriented Programming** (OOP) are distinct programming paradigms. While procedural programming is linear and task-centric, OOP emphasizes an organic model, where data is encapsulated in objects.

### Key Distinctions

#### Data & Function Management

- **Procedural**: Functions act on data. Data is often global, leading to potential conflicts.

- **OOP**: Data and functions are bundled within objects. Objects **interact through methods**, ensuring data integrity and encapsulation.

#### Code Abstraction and Reusability

- **Procedural**: Code is often segmented into functions. Global data can negatively affect reusability.

- **OOP**: Abstraction is achieved through classes and objects. Encapsulation helps create discrete, self-contained modules.

#### Inheritance and Polymorphism

- **Procedural**: Inheritance and polymorphism are absent.
- **OOP**: Inheritance fosters code reusability while polymorphism allows objects of different classes to be treated as instances of a shared superclass or interface.

#### OOP vs. Procedural in Different Languages

- **Procedural**: C is a prominent example. It's centered around the procedural approach where code is organized as a series of tasks or procedures. While C can emulate certain OOP features, like using `structs` to group related data, it doesn't inherently support the full spectrum of OOP.
- **OOP**: Java is intrinsically designed around OOP. It fully supports classes, inheritance, encapsulation, and other OOP principles.

In practice, many modern languages like Python, JavaScript, and C# support **multiple paradigms**, offering flexibility in choosing the right approach for a given task.

### Code Example: Procedural Approach

Here is the Python code:

```python
class Animal:
    def __init__(self, sound):
        self.sound = sound

def make_sound(animal):
    print(animal.sound)

dog = Animal("Woof")
cat = Animal("Meow")

make_sound(dog)
make_sound(cat)
```

### Code Example: Object-Oriented Approach

Here is the Java code:

```java
import java.util.ArrayList;
import java.util.List;

abstract class Animal {
    public abstract void makeSound();
}

class Dog extends Animal {
    public void makeSound() {
        System.out.println("Woof");
    }
}

class Cat extends Animal {
    public void makeSound() {
        System.out.println("Meow");
    }
}

public class Main {
    public static void main(String[] args) {
        List<Animal> animals = new ArrayList<>();
        animals.add(new Dog());
        animals.add(new Cat());

        for (Animal animal : animals) {
            animal.makeSound();
        }
    }
}
```
<br>

## 3. What is _encapsulation_?

**Encapsulation** is an object-oriented programming principle that combines data and methods that act on that data within a single unit, known as an **object**.

### Key Concepts

- **Information Hiding**: Encapsulation hides internal state and implementation details.

- **Access ControL**: Data is made available to external code only through defined methods: **getters** - for reading and **setters** - for writing.

- **Constraining Behavior**: Access methods can ensure that data adheres to specific rules (e.g., range checks or formatting standards).


### Benefits of Encapsulation

- **Security**: Offers controlled access to object data, reducing the risk of data corruption or unauthorized modifications.

- **Simplicity**: Objects abstract complex systems, presenting a simple interface for interaction.

- **Flexibility**: Encapsulation promotes loose coupling, making it easier to modify or replace object internals without impacting the external code.

### Practical Applications

- **Class Construction**: Modern programming languages like Java and C# follow an "encapsulation first" approach, utilizing access specifiers like `public`, `private`, and `protected`.

- **API Design**: As a software developer, encapsulating classes and modules helps create intuitive and focused APIs. It allows hiding internal strategies while exposing the desired functionality.

- **Testing**: Data hiding helps prevent direct access to object internals during testing, ensuring proper evaluation of object behavior through its public interface.

### Code Example: Encapsulation

Here is the Java code:

```java
public class Car {
    private int fuel;  // private ensures that fuel can't be accessed directly from outside the class

    public Car() {
        this.fuel = 100;  // Initialize with 100 units of fuel
    }

    // Getter method for fuel
    public int getFuel() {
        return fuel;
    }

    // Setter method for fuel with encapsulation enforcing constraints
    public void setFuel(int fuel) {
        if (fuel >= 0 && fuel <= 100) {
            this.fuel = fuel;
        } else {
            System.out.println("Invalid fuel amount.");
        }
    }

    public void drive() {
        if (fuel > 0) {
            fuel--;
            System.out.println("Vroom!");
        } else {
            System.out.println("Out of fuel!");
        }
    }

    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.drive();
        System.out.println("Fuel remaining: " + myCar.getFuel());
        myCar.setFuel(120);  // This will print "Invalid fuel amount."
    }
}
```
<br>

## 4. What is _polymorphism_? Explain _overriding_ and _overloading_.

**Polymorphism** in object-oriented programming allows objects of different types to be treated as if they belong to the same type through a **shared interface**. It abstracts method details, promoting code flexibility and reusability.

### Core Concepts

#### Overloading (Compile-time Polymorphism)

**Multiple methods** in the same class can have the same name but different parameters, allowing them to coexist. The compiler selects the appropriate method based on the method signature.

#### Code Example: Overloading

Here is the Java code:

```java
public class Sum {
    public int add(int a, int b) {
        return a + b;
    }
  
    public double add(double a, double b) {
        return a + b;
    }
}
```

#### Overriding (Runtime Polymorphism)

A **subclass** provides a specific implementation of a method that is already defined in its parent class, effectively replacing the parent's version. The method to be called is determined during the program's execution.

#### Code Example: Overriding

Here is the Python code:

```python
class Animal:
    def speak(self):
        return "Animal speaks"
  
class Cat(Animal):
    def speak(self):
        return "Cat meows"

obj_cat = Cat()
print(obj_cat.speak())  # Output: Cat meows
```

#### Virtual Methods (in languages like C++)

Methods marked `virtual` in the base class can be overridden in derived classes. They enable **dynamic dispatch**, ensuring the correct method is called, even through base class references.

#### Code Example: Virtual Methods

Here is the C++ code:

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void speak() {
        cout << "Animal speaks";
    }
};

class Cat : public Animal {
public:
    void speak() override {
        cout << "Cat meows";
    }
};
```

### Dynamic Dispatch and Late Binding

Polymorphism often leverages **dynamic dispatch**, a mechanism that determines at runtime which specific method to invoke.

This is also known as **late binding**. This feature enables generic code that can handle multiple object types, enriching flexibility and adaptability.
<br>

## 5. What is _inheritance_? Name some _types of inheritance_.

**Inheritance** is a fundamental concept in object-oriented programming that allows for the creation of **new classes** based on existing ones.

Inheritance establishes an **"is-a" relationship**, where the derived class (also called the **subclass** or **child class**) inherits properties and behaviors from its parent, or **base class**.

### Types of Inheritance

1. **Single Inheritance**: A class inherits from only one base class. Common in languages like Java.
   
   Example: Class `B` inherits from class `A`.

2. **Multiple Inheritance**: A class inherits from multiple base classes. While C++ supports it, languages like Java use interfaces to achieve a similar effect without the complexities associated with the "diamond problem."
   
   Example: Class `C` inherits from both classes `A` and `B`.

3. **Multilevel Inheritance**: A class inherits from another class, which itself is a derived class.
   
   Example: Class `C` inherits from class `B`, which inherits from class `A`.

4. **Hierarchical Inheritance**: One base class is inherited by multiple subclasses.
   
   Example: Both classes `B` and `C` inherit from class `A`.

5. **Hybrid Inheritance**: A combination of two or more of the above inheritance types. Its use can lead to complexities.
   
   Example: In C++, a class can be involved in both multiple and multilevel inheritances.

### Code Example: Different Types of Inheritance

Here is the Java code:

```java
// Single Inheritance
class A {
    void funcA() {
        System.out.println("Function of class A");
    }
}

class B extends A { }  // Class B inherits from class A


// Multiple Inheritance using interfaces
interface X {
    void funcX();
}

interface Y {
    void funcY();
}

class Z implements X, Y {  // Class Z implements both interface X and interface Y
    public void funcX() {
        System.out.println("Function of interface X");
    }

    public void funcY() {
        System.out.println("Function of interface Y");
    }
}


// Multilevel Inheritance
class A {
    void funcA() {
        System.out.println("Function of class A");
    }
}

class B extends A {
    void funcB() {
        System.out.println("Function of class B");
    }
}

class C extends B { }  // Class C inherits from class B, which inherits from class A


// Hierarchical Inheritance
class H {
    void funcH() {
        System.out.println("Function of class H");
    }
}

class I extends H { }  // Class I inherits from class H

class J extends H { }  // Class J also inherits from class H


// Java does not directly support hybrid inheritance through classes.
// However, you can achieve something similar using interfaces, as shown with multiple inheritance.
```
<br>

## 6. What is an _abstraction_? Name some _abstraction techniques_.

**Abstraction** in object-oriented programming (OOP) is the concept of focusing on essential characteristics and hiding unnecessary details.

It enables clear separation between high-level concepts and their specific implementations, promoting **code reusability**, **maintainability**, and **security**.

### Abstraction Techniques

#### Abstract Classes

- **Definition**: An abstract class is a class that cannot be instantiated on its own. It serves as a foundation for other classes.
- **Purpose**: Abstract classes allow you to define base behaviors that can be overridden by derived classes, while also allowing you to provide some default implementations. This means that while you define certain methods as abstract (no implementation), others can have actual code.
- **Use Case**: If you have a set of functionalities where some methods have a default behavior but can be overridden, and others must be defined by any child class, you'd use an abstract class.

#### Interfaces

- **Definition**: An interface is a contract or blueprint that classes adhere to. Unlike abstract classes, interfaces have no implementation details; they only declare method and property signatures.
- **Purpose**: Interfaces ensure a certain set of methods or properties exist in the classes that implement them. They guarantee a specific structure or behavior without dictating how that behavior is achieved.
- **Use Case**: When you want multiple classes to adhere to a specific contract, ensuring they all have the same methods (but possibly different implementations), you'd use an interface.

### Code Example: Abstraction Techniques

Here is the Java code:

```java
// Abstract Class
abstract class Vehicle {
    // Abstract method (no body)
    public abstract String start();

    // Regular method
    public String stop() {
        return "Vehicle stopped!";
    }
}

// Implementing the abstract class
class Car extends Vehicle {
    @Override
    public String start() {
        return "Car started!";
    }
}

// Interface
interface Drivable {
    // All methods in an interface are implicitly abstract
    void drive();
}

// Implementing both the abstract class and the interface
class Bike extends Vehicle implements Drivable {
    @Override
    public String start() {
        return "Bike started!";
    }

    @Override
    public void drive() {
        System.out.println("Bike is being driven!");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        System.out.println(car.start()); // Output: Car started!
        System.out.println(car.stop());  // Output: Vehicle stopped!

        Bike bike = new Bike();
        System.out.println(bike.start()); // Output: Bike started!
        bike.drive();                     // Output: Bike is being driven!
    }
}
```
<br>

## 7. What is a _class_ in OOP?

**Class** in Object-Oriented Programming represents a blueprint for creating objects (instances). It encapsulates attributes (data) and behaviors (methods) under a unified structure.

When instantiated, each **object** can carry individual data, adhering to the blueprint provided by its class.

### Key Components of a Class

- **Attributes**: They store the state of an object and can have varying data types.

- **Methods**: These are functions defined within the class, designed to operate on attributes or perform specific behaviors.

### OOP Principles in Classes

- **Inheritance**: Allows a subclass (child class) to inherit attributes and methods from a superclass (parent class).

- **Encapsulation**: Attributes and methods are bundled within a class, limiting direct access to ensure data safety.

- **Polymorphism**: Allows objects of different classes that implement the same interface to be used in a consistent manner.

- **Abstraction**: Hides internal details, providing a simplified interface. Achieved in classes by exposing only essential methods.

### Code Example: The Car Class

Here is the Python code:

```python
class Car:
    """A class to represent a car."""
    
    def __init__(self, make, model, year):
        """Initialize car attributes."""
        self.make = make
        self.model = model
        self.year = year
        self.fuel = 0

    def fill_tank(self, gallons):
        """Add fuel to the tank. Ensure the amount is positive."""
        if gallons > 0:
            self.fuel += gallons
        else:
            print("Invalid fuel amount.")

    def drive(self, distance=1):
        """Drive the car, consuming fuel based on distance."""
        if self.fuel >= distance:
            self.fuel -= distance
            print(f"Car drove {distance} unit(s). Remaining fuel: {self.fuel} units.")
        else:
            print("Insufficient fuel.")

# Create a Car object
my_car = Car("Honda", "Civic", 2022)

# Access its attributes and methods
my_car.fill_tank(10)

for _ in range(15):
    my_car.drive()
```

<br>

## 8. What is an _object_ in OOP?

An **object** represents a specific instance of a **class**. It encapsulates both **data** (attributes) and **behavior** (methods) within a single unit.

### Core Characteristics

- **Identity**: Each object has a unique identity that distinguishes it from others.
- **State**: Defined by its attributes, an object's state can change throughout its existence.
- **Behavior**: The methods associated with the object describe its possible actions or operations.

### Lifecycle of an Object

1. **Creation**: Objects are created from a class through a process called instantiation.
2. **Manipulation**: They may undergo state changes as attributes are modified, and methods are invoked.
3. **Destruction**: Terminates the object's existence, often handled automatically by the programming language ("garbage collection") or explicitly through code.

### Code Example: Object Instantiation

Here is the Python code:

``` python
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed

    def bark(self):
        print("Woof!")

myDog = Dog("Buddy", "Golden Retriever")
```
<br>

## 9. How do _access specifiers_ work and what are they typically?

In Object-Oriented Programming (OOP), **access specifiers** define the level of visibility and accessibility of class members.

### Types of Access Specifiers

1. **Private**: Members are only accessible within the defining class, ensuring data encapsulation.
2. **Protected**: Members are accessible within the defining class and its subclasses.
3. **Public**: Members are globally accessible to all classes.

### Code Example: Access Specifiers

Here is the Java code:

```java
public class Car {
    private String make;  // Accessible only within class
    protected int year;   // Accessible within class and subclasses
    double price;         // Default visibility: package-private
    
    public void setMake(String make) {
        this.make = make;
    }

    public String getMake() {
        return make;
    }

    protected void startEngine() {
       System.out.println("Engine started!");
    }
}
```

### Key Concepts

- **Data Encapsulation**: It ensures data integrity by hiding the class's internal state and **exposing it through methods**. This enables better control over the data and its access.

- **Inheritance and Abstraction**: Access levels regulate visibility in the context of inheritance, allowing classes to interact while preserving encapsulation.

### Common Mistakes

- **Excessive Use of Getter/Setter Pairs**: While they are useful for protecting data, avoid introducing methods that do not provide added functionality.
  
- **Needless Use of Public Members**: If a member does not require global access, consider using more restrictive access levels for better encapsulation.

### Best Practices

- **Favor Composition Over Inheritance**: If classes are loosely related, hiding details and components ensures better code maintenance.

- **Private by Default**: Encapsulate whenever possible. By default, members should be private, and their visibility be broadened only if necessary.

- **Minimal Use of Public Members**: Use them sparingly for elements that genuinely need global access.

- **Consistent Visibility**: Aim for uniform visibility within a class to avoid confusion.
<br>

## 10. Name some ways to _overload_ a _method_.

Let's look at three common techniques to **overload** a method.

### 1. Changing Parameter Number

This method involves altering the number of parameters in different method signatures.

Here is an example in Java:

```java
public int calculateSum(int a, int b) { // Two parameters
    return a + b;
}

public int calculateSum(int a, int b, int c) { // Three parameters
    return a + b + c;
}
```

### 2. Adapting Parameter Order

Another overloading technique involves rearranging the **order of parameters** in methods to create unique signatures.

Here is an example in Java:

```java
public double calculateArea(double length, double width) { // Length, then width
    return length * width;
}

public double calculateArea(double radius) { // Just radius for a circle
    return Math.PI * radius * radius;
}
```

### 3. Varying Parameter Type

You can define methods with different types of parameters to enable **overloading**.

Here is an example in Java:

```java
public void printDetails(String name, int age) {
    System.out.println("Name: " + name + " , Age: " + age);
}

public void printDetails(int id) {
    System.out.println("ID: " + id);
}

public void printDetails(double salary) {
    System.out.println("Salary: " + salary);
}
```
<br>

## 11. What is _cohesion_ in OOP?

**Cohesion** in OOP refers to how closely the methods and data within a single class are related to one another. A highly cohesive class is focused on a specific task or responsibility, making it easier to maintain, understand, and ensure reliability.

**High cohesion** is a desired attribute because it means that methods and properties within a class work together in a unified manner. In contrast, **low cohesion** indicates that a class has multiple, often unrelated responsibilities, making it harder to understand and maintain.

### Levels of Cohesion

1. **Coincidental**: Methods and properties within the class have no meaningful relationship.
2. **Logical**: Methods are grouped based on some logic but lack a clear theme.
3. **Temporal**: Methods are related by when they are executed, e.g., initialization methods.
4. **Procedural**: Methods are executed in a specific sequence.
5. **Communicational**: Methods work on the same set of data.
6. **Sequential**: The output of one method serves as the input for another.
7. **Functional**: All methods in the class contribute to a single well-defined task.

Of these, functional cohesion is the most desirable, as it closely aligns with the **Single Responsibility Principle**.

### Code Example: Low Cohesion Levels

Here is the Java code:

```java
public class FileUtility {

    public String readFile(String fileName) {
        // Read a file
        return content;
    }

    public void writeToDatabase(String data) {
        // Write content to a database
    }

    public void clearCache() {
        // Clear application cache
    }

    public List<String> parseFile(String content) {
        // Parse file content
        return parsedData;
    }
}
```

This `FileUtility` class exhibits low cohesion as it mixes file operations, database writing, and cache management.

### Recommendations for Improving Cohesion

1. **Single Responsibility Principle (SRP)**: Each class should have only one reason to change. This principle suggests that a class should focus on one task or responsibility.
2. **Encapsulation**: Encourage data hiding, and expose data only through focused and related methods.
<br>

## 12. What is _coupling_ in OOP?

**Coupling** in OOP describes the degree of interdependence between classes or modules. It determines how closely different modules or classes are linked to each other, impacting the system's flexibility, maintainability, and testability.

**Loose coupling** is generally preferred in software design.

### Types of Coupling

1. **Content Coupling**: This is the strongest form of coupling where one module directly accesses or modifies another module's internal data.

2. **Common Coupling**: Multiple modules share access to common global data. Any change to this shared resource can affect all the modules that depend on it.

3. **Control Coupling**: One module controls the flow of another by passing it control information, such as using flags.

4. **External Coupling**: Classes or modules are linked by external factors, such as configuration files or data schemas.

5. **Stamp (or Data) Coupling**: Modules share data structures and use only parts of them, requiring knowledge about the structure of the data being passed.

6. **Message Coupling**: The lowest form of coupling where modules communicate only through standard interfaces, such as method calls or messages.

### Relationship with SOLID Principles

- **Single Responsibility Principle (SRP)**: Adhering to SRP typically results in **low coupling** since classes have a singular focus, thereby minimizing dependencies.

- **Open-Closed Principle (OCP)**: Emphasizing extensibility without modification, OCP reduces the risk of **tight coupling** as extensions are typically made through interfaces or abstract classes.

- **Liskov Substitution Principle (LSP)**: When derived classes can replace their base classes without side effects, there's often a **reduction in coupling**, ensuring modules can operate independently of the specific derived class in use.

- **Interface Segregation Principle (ISP)**: By endorsing focused interfaces rather than "one-size-fits-all" ones, ISP naturally leads to **decreased coupling** as classes aren't forced to depend on methods they don't use.

- **Dependency Inversion Principle (DIP)**: By relying on abstractions rather than concrete implementations, DIP promotes **low coupling**, making systems more modular and adaptable.
<br>

## 13. What is a _constructor_ and how is it used?

A **constructor** is a special method in **object-oriented programming** used for initializing objects. It ensures that **newly created** objects are set up with appropriate initial state and any required resources.

### Key Concepts

#### Purpose

- A constructor ensures that an object is in a consistent state when created.
- It initializes and configures the object's attributes or fields.

#### Characteristics

- **Matches Object Definitions**: Each class defines one or more contructors for its objects.
- **Has a Class Name**: Constructors are named after the class, making them easy to identify.
- **No Return Type**: They don't return a value, not even `void`.
- **Automatic Invocation**: They are invoked or 'called' when an object is created.

#### Types of Constructors

1. **Default Constructors**:
   - No parameters.
   - Automatically provided by the language if no constructor is defined.
  
2. **Parameterized Constructors**:
   - Accept parameters for custom initialization.
   - Often used to provide initial values to internal attributes or fields.

3. **Copy Constructors**:
   - Accept another object of the same type and initialize the current object using values from it.
   - Commonly used for deep copying in languages like C++.

4. **Static Constructors**:
   - Used to initialize static member variables or for other class-level actions.
   - They don't take part in the creation of objects and can be absent in many OOP languages.

#### Code Examples: Constructors

Here is the Java code:

```java
class Vehicle {
    private String vehicleType;
    private int wheels;

    // Default Constructor
    public Vehicle() {
        vehicleType = "Car";
        wheels = 4;
    }

    // Parameterized Constructor
    public Vehicle(String type, int wheelCount) {
        vehicleType = type;
        wheels = wheelCount;
    }

    public void showDetails() {
        System.out.println("Type of Vehicle: " + vehicleType);
        System.out.println("Number of Wheels: " + wheels);
    }

    public static void main(String[] args) {
        // Calling Default Constructor
        Vehicle car = new Vehicle();
        car.showDetails();

        // Calling Parameterized Constructor
        Vehicle bike = new Vehicle("Bike", 2);
        bike.showDetails();
    }
}
```

Here is a C++ code:

```cpp
#include <iostream>
using namespace std;

class Person {
    private:
        string name;
        int age;

    public:
        // Parameterized Constructor
        Person(string n, int a) {
            name = n;
            age = a;
        }

        void displayInfo() {
            cout << "Name: " << name << ", Age: " << age << endl;
        }
};

int main() {
    // Calling Parameterized Constructor
    Person p1 = Person("Alice", 25);
    p1.displayInfo();

    return 0;
}
```

Here is a C# code:

```csharp
using System;

class Car {
    private string model;

    // Parameterized Constructor
    public Car(string m) {
        model = m;
    }

    static void Main() {
        // Calling Parameterized Constructor
        Car c = new Car("Toyota");
        Console.WriteLine("Car Model: " + c.model);
    }
}
```
<br>

## 14. Describe the concept of _destructor_ or _finalizer_ in OOP.

**Destructors**, or class **finalizers**, are used in **object-oriented programming** to perform cleanup actions before an object is destroyed.

### Object Destruction

Objects can be **explicitly** or **implicitly** destroyed:

- **Explicit**: The programmer calls a destructing function or method. Languages like C++ use a destructor.
- **Implicit**: The language or environment manages object destruction. Garbage collectors in Java, C#, and Python are examples.

### Destructors

A **destructor** is a special method that is automatically called right before an object goes out of scope or is explicitly destroyed. Its primary purpose is to release resources or perform other cleanup tasks, like closing files or releasing memory.

#### Use Cases

- **Resource Management**: Ensuring timely release of system resources.
- **Memory Management**: Helpful in non-garbage collected languages to prevent memory leaks.
- **Logging Exit or Cleanup Actions**: Commonly used to log an object's destruction or clean-up steps.

### Garbage Collection

For memory management, garbage collection is a mechanism that specifically targets automatic memory reclamation. In languages like Java and C#, destructors may not be necessary due to reliable garbage collectors.

#### Note for Java Developers

Java introduced the `finalize()` method, which is similar to a destructor. It's often discouraged in favor of using the `AutoCloseable` interface and the `try-with-resources` statement for enhanced resource management.

#### Code Example: C++

Here is the C++ code:

```cpp
class Resource {
public:
    Resource() { std::cout << "Resource Acquired\n"; }
    ~Resource() { std::cout << "Resource Destroyed\n"; }
};

int main() {
    Resource r;
}  // Destructs r here
```

### Non-Memory Resources

Destructors can manage a variety of resources in addition to memory, such as:

- **Files**: Ensuring files are closed to avoid data loss.
- **Network Connections**: Closing sockets to prevent resource leaks.
- **Database Connections**: Helpful in releasing database locks or sessions.
- **Hardware Devices**: For devices like cameras or sensors, freeing resources ensures they are available for other applications.

#### Code Example: Resource Management

Here is the C++ code:

```cpp
#include <iostream>
#include <fstream>

class FileHandler {
public:
    std::ofstream file;
    FileHandler(std::string fileName) {
        file.open(fileName);
        if (file.is_open()) {
            std::cout << "File Opened\n";
        }
    }
    ~FileHandler() {
        if (file.is_open()) {
            file.close();
            std::cout << "File Closed\n";
        }
    }
};

int main() {
    FileHandler fh("sample.txt");
}  // Destructor called on fh, closes the file
```
<br>

## 15. Compare _inheritance_ vs. _mixin_ vs. _composition_.

**Inheritance**, **mixins**, and **composition** are all techniques in object-oriented programming that deal with code reuse and the relationship between objects or classes.

Let's look into the details and compare them:

### Inheritance

- **Definition**: A class (subclass) inherits properties and behaviors from another class (superclass).
- **Relationship**: "is-a" (e.g., a `Car` is a `Vehicle`).
- **Pros**: Direct way to reuse code; establishes intuitive relationships.
- **Cons**: Can lead to complex hierarchies; potential for over-generalization.

### Mixin

- **Definition**: A class that offers methods to other classes without being a standalone entity. Common in languages without multiple inheritance, such as Python.
- **Relationship**: "kind-of-a" or "can-do-this" (e.g., a `Helicopter` can fly like a `Bird`).
- **Pros**: Reuses code across classes; avoids deep inheritance issues.
- **Cons**: Method source can be unclear; potential name clashes.

### Composition

- **Definition**: Building objects by combining simpler ones. Emphasizes a "has-a" relationship.
- **Relationship**: "has-a" (e.g., a `Car` has an `Engine`).
- **Pros**: Encourages modular design; components can be easily swapped.
- **Cons**: May need more design upfront; can require more boilerplate code.

Many modern OOP design guidelines, like the **composition over inheritance principle**, suggest that unless there's a clear "is-a" relationship, it's often better to use **composition** as it's more flexible and leads to a more modular and maintainable design.
<br>



#### Explore all 52 answers here 👉 [Devinterview.io - OOP](https://devinterview.io/questions/web-and-mobile-development/oop-interview-questions)

<br>

<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

