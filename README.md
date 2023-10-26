# ⚫ OOP in Tech Interviews 2024: 39 Must-Know Questions & Answers

**Object-Oriented Programming** is recognized for enabling structured and scalable code in tech.

Check out our carefully selected list of **basic** and **advanced** OOP questions to be well-prepared for your tech interviews in 2024.

![OOP Decorative Image](https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/blogImg%2FoopBlogImg.png?alt=media&token=6162bebd-1639-4378-a4ce-bc2f13e4ffe6&_gl=1*ijb4zt*_ga*OTYzMjY5NTkwLjE2ODg8NDM8Njg.*_ga_CW55HF8NVT*MTY5ODMxNjI0Ny4xODEuMS4xNjk8MzE6OTY0LjM6LjAuMA..)

👉🏼 You can also find all answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 1. What is _Object-Oriented Programming_ (OOP)?

### Answer

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

---


## 🔹 2. What is the difference between _Procedural_ and _Object-Oriented_ programming?

### Answer

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

---


## 🔹 3. What is a _Class_?

### Answer

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


---


## 🔹 4. What is an _Object_?

### Answer

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

---


## 🔹 5. Explain the _Hierarchical Relationship_ between classes.

### Answer

In OOP, **classes** are often organized in a **hierarchical** manner through inheritance. This hierarchy establishes relationships where specific classes are built upon more general ones, refining or extending their characteristics and behaviors.

### Key Concepts

- **Base and Derived Classes**: The base (or parent) class provides a foundational set of attributes and methods. Derived (or child) classes inherit from the base class, adapting or expanding upon its defined characteristics.

- **Inheritance Chain**: This represents the sequence of derived classes from a base class. A derived class can itself be a base class for another, leading to multiple layers in the hierarchy.

### Visual Representation

![Class Hierarchy](https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/oop%2Fclass-hierarchy%20(1).jpg?alt=media&token=f14cea00-085b-4cb8-b440-860302f0fa16&_gl=1*16lln2r*_ga*OTYzMjY5NTkwLjE2ODg4NDM4Njg.*_ga_CW55HF8NVT*MTY5ODA3NDc5OC4xNzMuMS4xNjk4MDc1MDcxLjU2LjAuMA..)

### Code Example: Class Hierarchy

Here is the Python code:

```python
class Animal:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def eat(self):
        print(f"{self.name} is eating.")

class Mammal(Animal):
    def sleep(self):
        print(f"{self.name} is sleeping.")

class Bird(Animal):
    def fly(self):
        print(f"{self.name} is flying.")

class Lion(Mammal):
    def __init__(self, name, age, gender):
        super().__init__(name, age)
        self.gender = gender

    def roar(self):
        print(f"{self.name} is roaring.")

class Whale(Mammal):
    def swim(self):
        print(f"{self.name} is swimming.")

class Penguin(Bird):
    def walk(self):
        print(f"{self.name} is walking on land.")
```

---


## 🔹 6. What is the difference between a _Method_ and a _Function_ in the context of _OOP_?

### Answer

**Methods** and **functions** are both means to group code for reuse in OOP, but they serve different roles based on where and how they are used.

While all methods are functions in a broader sense, not all functions are methods. The distinction lies in their relationship (or lack thereof) to class instances.

### Methods: Object-Linked Behavior

- **What**: Methods are functions that are defined within a **class** and are associated with object behavior. They are designed to manipulate or interact with the class's instance data (attributes).
  
- **Invocation**: Methods are invoked on an instance of a class using dot notation, e.g., `my_object.my_method()`.
  
- **Access**: Methods inherently have access to the object's data and other methods. In many OOP languages, this is done through a self-reference (like `self` in Python or `this` in Java).
  
- **Example**: Consider a `Car` class. The actions `start_engine` and `change_gear` would be methods, tailored to the state and behavior of specific car instances.

### Functions: Class-Agnostic Procedures

- **What**: In the OOP context, functions can be defined within a class but aren't tied to an instance's behavior or data. Such functions might be static methods in some languages, meaning they relate to the class rather than any specific instance.
  
- **Invocation**: Functions, even if part of a class, are typically called without requiring an instance. In some languages, this might require special notation, like using the `@staticmethod` decorator in Python.
  
- **Access**: Functions within a class context don't typically access or modify instance-specific data unless passed that data explicitly.
  
- **Example**: Inside a `Math` class, a function `square_root` would be a general utility that computes the square root of a number. It doesn't operate on instance data and doesn't need to know about specific `Math` objects.

---


## 🔹 7. What is _Inheritance_? Name some _Types of Inheritance_.

### Answer

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

---


## 🔹 8. Compare _Inheritance_ vs. _Mixin_ vs. _Composition_.

### Answer

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

---


## 🔹 9. Can you inherit _Private Members_ of a _Class_?

### Answer

While both **public** and **protected** members can be inherited by derived classes in **OOP**, this is **not** the case for **private** members.

In most OOP languages these members are **not accessible** outside their declaring class.

---


## 🔹 10. Can a _Class_ inherit the _Constructor_ of its _Base Class_?

### Answer

While traditionally **constructors are not inherited** by derived classes, some languages offer mechanisms to manage constructor behavior, such as **constructor chaining**.

### Constructor Inheritance in Different Languages

- **C++**: Constructors aren't inherited, but you can use constructor initializer lists to invoke a base class constructor.
  
- **Java**: Constructors aren't inherited, but if a derived class constructor doesn't explicitly invoke a base class constructor, the no-argument base class constructor is called automatically.

- **Python**: Making use of the `super()` mechanism ensures appropriate base class constructor invocations across the inheritance hierarchy.

- **C#**: Constructors are not inherited, but derived classes can use the `base` keyword to call a constructor from the base class. If a derived class does not explicitly define any constructors, the default constructor of the base class is automatically invoked.

- **Swift**: Constructors aren't inherited. However, Swift introduces designated and convenience initializers for class construction and proper initialization across inheritance.

- **Kotlin**: Constructors aren't inherited, but derived classes need to invoke the base class constructor using the `super` keyword.

---

---

## 🔹 11. How to prevent a _Class_ to be _Inherited_ further?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 12. What is _Encapsulation_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 13. What is _Polymorphism_? Explain _Overriding_ and _Overloading_.

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 14. Name some ways to _Overload_ a _Method_.

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 15. What is an _Abstraction_? Name some _Abstraction Techniques_.

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 16. What is an _Abstract Class_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 17. What is an _Interface_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 18. When to use _Interface_ vs. _Base Class_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 19. Why can't _Static Methods_ in _C#_ implement an _Interface_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 20. Can a _Non-static_ method be overridden as _Static_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 21. Can you set _Accessibility Modifiers_ for methods within an _Interface_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 22. Explain the concepts of _Constructor_ and _Destructor_.

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 23. What is a _Static Constructor_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 24. Why might a _Destructor_ in a _C#_ class not execute?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 25. What is the difference between a _Class_ and a _Structure_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 26. What is the difference between _Virtual method_ and _Abstract method_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 27. What is the purpose of a _Virtual keyword_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 28. What is _Cohesion_ in OOP?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 29. What is _Coupling_ in OOP?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 30. What is the difference between _Cohesion_ and _Coupling_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 31. How do _Association_, _Aggregation_, and _Composition_ differ in OOP?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 32. What is _Liskov Substitution Principle_ (LSP)? Provide some examples of _Violation_ and _Adherence_.

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 33. Whait is _Repository Pattern_? Name some of it's benefits.

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 34. How _Monads_ can be useful in _OOP_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 35. What is a _Unit Of Work_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 36. Does _.NET_ support _Multiple Inheritance_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 37. Why use _Getters_ and _Setters_ for simple operations instead of _Public Fields_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 38. What is _Circular Reference_? How to solve it?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)

---

## 🔹 39. Is it possible to declare a _Private Class_ within a _Namespace_?

### Answer

👉🏼 Check out all 39 answers here: [Devinterview.io - OOP](https://devinterview.io/dev/oop-interview-questions)
