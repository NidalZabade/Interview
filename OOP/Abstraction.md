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

# Abstraction

## What is Abstraction?

**Abstraction** is a process of hiding the implementation details and showing only functionality to the user. In other words, the user will have the information on what the object does instead of how it does it.

## How to use Abstraction?

To use abstraction, you must create an abstract class or an [**interface**](Interface.md).

### Abstract Class

An **abstract class** is a restricted [class](Class.md#class) that cannot be used to create objects (to access it, it must be inherited from another class).

To access an abstract class, it must be inherited from another class, providing the implementation of the abstract methods in it.

```java

// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Cat extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The cat says: meow meow");
  }
}

class Main {
  public static void main(String[] args) {
    Cat myCat = new Cat(); // Create a Cat object
    myCat.animalSound(); // Call the abstract method animalSound()
    myCat.sleep(); // Call the regular method sleep()
  }
}

```

## Rules for Abstract Class

* An abstract class must be declared with an `abstract` keyword.
* It can have abstract and non-abstract methods.
* It cannot be instantiated.
* A subclass must provide the implementation of abstract methods of the parent abstract class (<red>**Override the abstract method**</red>).

## Abstract vs [Interface](Interface.md#interface)

| Interface | Abstract Class |
| --- | --- |
| An interface is a completely "abstract class" that is used to group related methods with empty bodies. | An abstract class is a class that is declared abstract—it may or may not include abstract methods. |
| An interface is not a class. | An abstract class is a class. |
| An interface cannot be used to create objects (in the example above, it is not possible to create an "Animal" object in the MyMainClass). | An abstract class can be used to create objects. |
| On the other hand, an abstract class can contain a fully implemented method. | An interface can only contain abstract methods. |
| An interface can extend another interface, just like the way a class can inherit from another class. | An abstract class can extend another class and implement multiple interfaces. |
| An interface can be used with the `implements` keyword (see example above). | An abstract class can be used with the `extends` keyword. |

[**Go back**](Overview.md#oop)