# OOP Questions

## Table of Contents

- [OOP Questions](#oop-questions)
  - [Table of Contents](#table-of-contents)
    - [What is OOP?](#what-is-oop)
    - [What is class?](#what-is-class)
    - [What is object?](#what-is-object)
    - [What is the difference between an interface and an abstract class?](#what-is-the-difference-between-an-interface-and-an-abstract-class)
    - [What is Polymorphism?](#what-is-polymorphism)
    - [What is Encapsulation?](#what-is-encapsulation)
    - [What is the difference between == and equals()?](#what-is-the-difference-between--and-equals)
    - [What is the difference between a checked exception and an unchecked exception?](#what-is-the-difference-between-a-checked-exception-and-an-unchecked-exception)
    - [What is the difference between a final, finally, and finalize?](#what-is-the-difference-between-a-final-finally-and-finalize)
    - [What is the difference between a static and a non-static variable?](#what-is-the-difference-between-a-static-and-a-non-static-variable)
    - [What is the difference between a constructor and a method?](#what-is-the-difference-between-a-constructor-and-a-method)
    - [What is the difference between a class and an object?](#what-is-the-difference-between-a-class-and-an-object)
    - [What is the difference between a class and an interface?](#what-is-the-difference-between-a-class-and-an-interface)
    - [What is the difference between a mutable and an immutable object?](#what-is-the-difference-between-a-mutable-and-an-immutable-object)
    - [Represent a family consisting of a father, mother, and children using OOP.](#represent-a-family-consisting-of-a-father-mother-and-children-using-oop)
    - [What is the SOLID principle?](#what-is-the-solid-principle)

<br><br/>

### [What is OOP?](../OOP/README.md#what-is-oop)

### [What is class?](../OOP/Class.md#what-is-a-class)

### [What is object?](../OOP/Class.md#object)

### [What is the difference between an interface and an abstract class?](../OOP/Abstraction.md#abstract-vs-interface)

### [What is Polymorphism?](../OOP/Polymorphism.md#what-is-polymorphism)

### [What is Encapsulation?](../OOP/Encapsulation.md#what-is-encapsulation)

### What is the difference between == and equals()?

Ans: == is used to compare primitive types and references. equals() is used to compare objects.

For example:

```java
    String s1 = "Hello";
    String s2 = "Hello";
    String s3 = new String("Hello");

    System.out.println(s1 == s2); // true
    System.out.println(s1 == s3); // false
    System.out.println(s1.equals(s3)); // true
    System.out.println(s1.equals(s2)); // true
```

### What is the difference between a checked exception and an unchecked exception?

Ans: Checked exceptions are checked at compile time. Unchecked exceptions are checked at runtime.

For example:

```java
    public void readFile() throws IOException {
        // code to read file
    }
```

In the above example, IOException is a checked exception. If the code in readFile() throws an IOException, then the readFile() method must either handle the exception or declare that it throws the exception. If readFile() does not handle the exception or declare that it throws the exception, then the code will not compile.

```java
    public void readFile() {
        // code to read file
    }
```

In the above example, there is no checked exception. If the code in readFile() throws an exception, then the readFile() method must either handle the exception or declare that it throws the exception. If readFile() does not handle the exception or declare that it throws the exception, then the code will compile.

### What is the difference between a final, finally, and finalize?

Ans: final is a keyword used to make a variable constant. finally is a block that is always executed whether an exception is handled or not. finalize is a method that is called by the garbage collector on an object before garbage collection.

### What is the difference between a static and a non-static variable?

Ans: A static variable is shared by all the objects of the class. A non-static variable is not shared by all the objects of the class.

### What is the difference between a constructor and a method?

Ans: A constructor is used to initialize the object. A method is used to perform some operations.

### What is the difference between a class and an object?

Ans: A class is a blueprint from which objects are created. An object is an instance of a class.

### What is the difference between a class and an interface?

Ans: A class can have both abstract and concrete methods. An interface can have only abstract methods.

### What is the difference between a mutable and an immutable object?

Ans: A mutable object can be changed after it is created. An immutable object cannot be changed after it is created.

### Represent a family consisting of a father, mother, and children using OOP.

```java
class Person {
    private String name;
    private int age;
    private Person father;
    private Person mother;

    public Person(String name, int age, Person father, Person mother) {
        this.name = name;
        this.age = age;
        this.father = father;
        this.mother = mother;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public Person getFather() {
        return father;
    }

    public Person getMother() {
        return mother;
    }

}

class Family {
    private Person father;
    private Person mother;
    private List<Person> children;

    public Family(Person father, Person mother, List<Person> children) {
        this.father = father;
        this.mother = mother;
        this.children = children;
    }

    public Person getFather() {
        return father;
    }

    public Person getMother() {
        return mother;
    }

    public List<Person> getChildren() {
        return children;
    }
}
```

### [What is the SOLID principle?](../OOP/SOLID.md#introduction)

[**Go Back**](README.md)
