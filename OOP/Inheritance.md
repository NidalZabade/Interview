
# Inheritance

## What is inheritance?

Inheritance is the procedure in which one [**class**](Class.md) inherits the attributes and methods of another class. The class whose properties are inherited is called the **superclass** or **parent class**. The class that inherits the properties of the superclass is called the **subclass** or **child class**.

## Why use inheritance?

Inheritance is used to express an **is-a** relationship. For example, a **dog** is an animal, a **cat** is an animal and an **Octopus** is an animal. So, the `dog`, `cat` and `Octopus` classes can inherit from the `animal` class.
all the animals has `legs`, also all animals can `eat`, `sleep`, `run`, etc. So, the **animal** class can have these methods and the `legs` attribute. The `dog`, `cat` and `Octopus` classes can inherit from the `animal` class.

## Types of inheritance

There are two types of inheritance in Java:

* **Single inheritance**: a class can only inherit from one superclass.
* **Multilevel inheritance**: a class can inherit from a subclass, which can inherit from another superclass.

### Superclass

The superclass is the class being inherited from, also called the **base class** or **parent class**.

### Subclass

The subclass is the class that inherits from another class, also called the **derived class** or **child class**.

## Inheritance example

```java
//Superclass
class Animal {

    //Attribute
    int legs;

    public Animal(int legs) {
        this.legs = legs;
    }

    public void eat() {
        System.out.println("I can eat");
    }
    public void sleep() {
        System.out.println("I can sleep");
    }
}

//Subclass
class Dog extends Animal {

    //Attribute
    String name;

    public Dog(String name) {
        super(4);
        this.name = name;
    }

    public void bark() {
        System.out.println("I can bark");
    }
}

//Subclass
class Octopus extends Animal {

    //Attribute
    Boolean hasInk;

    public Octopus(Boolean hasInk) {
        super(8);
        this.hasInk = hasInk;
    }

    public void swim() {
        System.out.println("I can swim");
    }
}

public class Main {

    public static void main(String[] args) {

        Dog dog = new Dog("Rex");
        dog.eat();
        dog.sleep();
        dog.bark();
        System.out.println("I have " + dog.legs + " legs");

        Octopus octopus = new Octopus(true);
        octopus.eat();
        octopus.sleep();
        octopus.swim();
        System.out.println("I have " + octopus.legs + " legs");
    }
}
```

## Inheritance rules

* A subclass can only inherit from one superclass.
* A subclass inherits all the public and protected members of its parent, no matter what package the subclass is in.
* A subclass does not inherit the private members of its parent class.
* The constructor of the superclass is called from the subclass using the `super()` keyword.
* The `super()` keyword must be the first statement in the subclass constructor.
* If the superclass has no default constructor, the subclass must call a constructor from the superclass using the `super()` keyword.
* A subclass can override any methods of its parent class.

[**Go back**](README.md#oop)