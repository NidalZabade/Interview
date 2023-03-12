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

# Polymorphism

## What is polymorphism?

**Polymorphism** is the ability of an [**object**](Class.md#object) to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object. and its an extension of [**inheritance**](Inheritance.md).

## How to use polymorphism?

To use polymorphism, you must create a **parent class** reference that is used to refer to a **child class** object.

```java
//Parent class
class Animal {
    public void animalSound() {
        System.out.println("The animal makes a sound");
    }
}

class cat extends Animal {
    public void animalSound() {
        System.out.println("The cat says: meow meow");
    }
}

class Dog extends Animal {
    public void animalSound() {
        System.out.println("The dog says: bow wow");
    }
}

class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Animal();  // Create a Animal object
        Animal myCat = new cat();  // Create a cat object
        Animal myDog = new Dog();  // Create a Dog object
        myAnimal.animalSound();
        myCat.animalSound();
        myDog.animalSound();
    }
}
```

Output:

```java
The animal makes a sound
The cat says: meow meow
The dog says: bow wow
```

[**Go back**](Overview.md#oop)