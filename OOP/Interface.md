<style>
red { color: Red }
orange { color: Orange }
green { color: Green }
blue { color: Blue }
yellow { color: Yellow }
magenta { color: Magenta }
cyan { color: Cyan }
gray { color: Gray }
</style>

# Interface

## What is Interface?

A **interface** is a reference type, similar to a [class](Class.md#class), that can contain only constants, method signatures, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods.

## Rules for Interface

* An interface is implicitly abstract. You do not need to use the `abstract` keyword while declaring an interface.
* Each method in an interface is also implicitly abstract, so the `abstract` keyword is not needed.
* Interface methods are implicitly public.


## How to use Interface?

To use interface, you must create a class that implements the interface.

```java
//Interface
interface Animal {
    public void animalSound(); // interface method (does not have a body)
    public void sleep(); // interface method (does not have a body)
}

// Cat "implements" the Animal interface

class Cat implements Animal {
    public void animalSound() {
        // The body of animalSound() is provided here
        System.out.println("The cat says: meow meow");
    }
    public void sleep() {
        // The body of sleep() is provided here
        System.out.println("Zzz");
    }
}

class Main {
    public static void main(String[] args) {
        Cat myCat = new Cat(); // Create a Cat object
        myCat.animalSound(); // Call the animalSound() method on the Cat object
        myCat.sleep(); // Call the sleep() method on the Cat object
    }
}
```

## Multiple Interfaces

A class can implement more than one interface.

```java
interface FirstInterface {
    public void myMethod(); // interface method
}

interface SecondInterface {
    public void myOtherMethod(); // interface method
}

// Implement multiple interfaces

class DemoClass implements FirstInterface, SecondInterface {
    public void myMethod() {
        System.out.println("Some text..");
    }
    public void myOtherMethod() {
        System.out.println("Some other text...");
    }
}

class Main {
    public static void main(String[] args) {
        DemoClass myObj = new DemoClass();
        myObj.myMethod();
        myObj.myOtherMethod();
    }
}
```

## Interface Inheritance

An interface can inherit another interface, in the same way as a class.

```java

interface FirstInterface {
    public void myMethod(); // interface method
}

interface SecondInterface extends FirstInterface {
    public void myOtherMethod(); // interface method
}

// Implement interface
class DemoClass implements SecondInterface {
    public void myMethod() {
        System.out.println("Some text..");
    }
    public void myOtherMethod() {
        System.out.println("Some other text...");
    }
}

class Main {
    public static void main(String[] args) {
        DemoClass myObj = new DemoClass();
        myObj.myMethod();
        myObj.myOtherMethod();
    }
}
```

## Interface vs [Abstract Class](Abstraction.md#abstraction)

| Interface | Abstract Class |
| --- | --- |
| An interface is a completely "abstract class" that is used to group related methods with empty bodies. | An abstract class is a class that is declared abstract—it may or may not include abstract methods. |
| An interface is not a class. | An abstract class is a class. |
| An interface cannot be used to create objects (in the example above, it is not possible to create an "Animal" object in the MyMainClass). | An abstract class can be used to create objects. |
| On the other hand, an abstract class can contain a fully implemented method. | An interface can only contain abstract methods. |
| An interface can extend another interface, just like the way a class can inherit from another class. | An abstract class can extend another class and implement multiple interfaces. |
| An interface can be used with the `implements` keyword (see example above). | An abstract class can be used with the `extends` keyword. |

[**Go back**](Overview.md#oop)