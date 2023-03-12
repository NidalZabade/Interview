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

# Class

## What is a class?

A class is a <blue>blueprint</blue> for creating objects (a particular data structure), providing initial values for state (member variables or attributes), and implementations of behavior (member functions or methods).

## Class components

* **Attributes**: variables that describe the state of the object
* **Methods**: functions that describe the behavior of the object
* **Constructor**: special method that is called when an object is created

### Class examples

#### Car class

```java
// class definition
class Car {
    // attributes
    String color;
    String brand;
    int speed;

    // constructor
    Car(String color, String brand, int speed) {
        this.color = color;
        this.brand = brand;
        this.speed = speed;
    }

    // methods
    void accelerate() {
        speed += 10;
    }

    void brake() {
        speed -= 10;
    }
}

```

#### Person class

```java
// class definition
class Person{
    String name;
    String address;
    int age;

    // constructor
    Person(String name, String address, int age) {
        this.name = name;
        this.address = address;
        this.age = age;
    }

    // methods
    void walk() {
        System.out.println(name + " is walking");
    }

    void eat() {
        System.out.println(name + " is eating");
    }
}

```

## Object

An object is an <red>**instance of a class**</red>. When a class is defined, no memory is allocated but when it is instantiated (i.e. an object is created) memory is allocated.

### Object example

```java

Car car1 = new Car("red", "BMW", 0);
Car car2 = new Car("blue", "Audi", 0);
Person person1 = new Person("John", "London", 20);
Person person2 = new Person("Mary", "Paris", 25);

```

## Class vs Object

* A class is a blueprint for creating objects.
* An object is an instance of a class.
* A class can be used to create many objects.
* An object belongs to a particular class.

[Go back](Overview.md#oop)
