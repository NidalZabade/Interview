# SOLID principles

## Table of Contents

- [SOLID principles](#solid-principles)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [The SOLID principles](#the-solid-principles)
    - [Single Responsibility Principle](#single-responsibility-principle)
      - [Example](#example)
    - [Open/Closed Principle](#openclosed-principle)
      - [Example](#example-1)
    - [Liskov Substitution Principle](#liskov-substitution-principle)
      - [Example](#example-2)
    - [Interface Segregation Principle](#interface-segregation-principle)
      - [Example](#example-3)
    - [Dependency Inversion Principle](#dependency-inversion-principle)
      - [Example](#example-4)

## Introduction

SOLID is an acronym for the first five object-oriented design (OOD) principles by Robert C. Martin, popularly known as Uncle Bob. These principles, when combined together, make it easy for a programmer to develop software that are easy to maintain and extend. This is done by making sure that each software module or class has responsibility over a single part of the functionality provided by the software, and that they interact with each other minimally.

## The SOLID principles

### Single Responsibility Principle

The Single Responsibility Principle (SRP) states that a class should have only one reason to change. In other words, a class should have only one job.

#### Example

- Example 1

```java

class Person {

    private String name;

    private String address;

    private String phone;

    public String getName() {

        return name;

    }

    public void setName(String name) {

        this.name = name;

    }

    public String getAddress() {

        return address;

    }

    public void setAddress(String address) {

        this.address = address;

    }

    public String getPhone() {

        return phone;

    }

    public void setPhone(String phone) {

        this.phone = phone;

    }

}

```

In the above example, the `Person` class has three reasons to change:

1. The `name` field is changed.
2. The `address` field is changed.
3. The `phone` field is changed.

Using the Single Responsibility Principle, we can refactor the `Person` class into three classes, each with a single responsibility:

```java

class Person {

    private Name name;

    private Address address;

    private Phone phone;

    public Name getName() {

        return name;

    }

    public void setName(Name name) {

        this.name = name;

    }

    public Address getAddress() {

        return address;

    }

    public void setAddress(Address address) {

        this.address = address;

    }

    public Phone getPhone() {

        return phone;

    }

    public void setPhone(Phone phone) {

        this.phone = phone;

    }

}

class Name {

    private String name;

    public String getName() {

        return name;

    }

    public void setName(String name) {

        this.name = name;

    }


}

class Address {

    private String address;

    public String getAddress() {

        return address;

    }

    public void setAddress(String address) {

        this.address = address;

    }

}

class Phone {

    private String phone;

    public String getPhone() {

        return phone;

    }

    public void setPhone(String phone) {

        this.phone = phone;

    }

}

```

The `Person` class now has a single responsibility: to represent a person. The `Name`, `Address`, and `Phone` classes now have a single responsibility: to represent a name, address, and phone number, respectively.

- Example 2

```java

class PaymentProcessor {

    public void charge(Payment payment) {

        // Charge the payment

    }

    public String createReport(Payment payment) {

        // Create a report for the payment

    }

    public void printReport(String report) {

        // Print the report

    }

    public void savePayment(Payment payment) {

        // Save the payment to the database

    }

}

```

In the above example, the `PaymentProcessor` class has three reasons to change:

1. The `createReport` method is changed.
2. The `savePayment` method is changed.
3. The `printReport` method is changed.

Using the Single Responsibility Principle, we can refactor the `PaymentProcessor` class into two classes, each with a single responsibility:

```java

class PaymentProcessor {

    private Payment payment;

    public Payment getPayment() {

        return payment;

    }

    public void setPayment(Payment payment) {

        this.payment = payment;

    }

    public void charge() {

        // Charge the payment, save the payment to the database, create a report for the payment and print the report

        // Charge the payment


        // Save the payment to the database
        SavePayment savePayment = new SavePayment();
        savePayment.savePayment(payment);

        // Create a report for the payment
        PaymentReport reportGenerator = new PaymentReport();
        String report = reportGenerator.createReport(payment);

        // Print the report
        reportGenerator.printReport(report);

    }

}

class PaymentReport {

    public String createReport(Payment payment) {

        // Create a report for the payment

    }

    public void printReport(String report) {

        // Print the report

    }

}

class SavePayment {

    public void savePayment(Payment payment) {

        // Save the payment to the database

    }

}

```

The `PaymentProcessor` class now has a single responsibility: to process a payment. The `ReportGenerator` class now has a single responsibility: to generate a report for a payment.

### Open/Closed Principle

The Open/Closed Principle (OCP) states that software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.

#### Example

```java

class PaymentProcessor {

    public void charge(Payment payment) {

        // Charge the payment

    }

    public String createReport(Payment payment) {

        // Create a report for the payment

    }

    public void printReport(String report) {

        // Print the report

    }

    public void savePayment(Payment payment) {

        // Save the payment to the database

    }

}

```

In the above example, the `PaymentProcessor` class is closed for modification. If we want to add a new payment method, we would have to modify the `PaymentProcessor` class. This violates the Open/Closed Principle.

Using the Open/Closed Principle, we can refactor the `PaymentProcessor` class into two classes, each with a single responsibility:

```java

class PaymentProcessor {

    private Payment payment;

    public Payment getPayment() {

        return payment;

    }

    public void setPayment(Payment payment) {

        this.payment = payment;

    }

    public void charge() {

        // Charge the payment, save the payment to the database, create a report for the payment and print the report

        // Charge the payment
        payment.charge();

        // Save the payment to the database
        SavePayment savePayment = new SavePayment();
        savePayment.savePayment(payment);

        // Create a report for the payment
        PaymentReport reportGenerator = new PaymentReport();
        String report = reportGenerator.createReport(payment);

        // Print the report
        reportGenerator.printReport(report);

    }

}

class Payment {

    public void charge() {

        // Charge the payment

    }

}

class PaymentReport {

    public String createReport(Payment payment) {

        // Create a report for the payment

    }

    public void printReport(String report) {

        // Print the report

    }

}

class SavePayment {

    public void savePayment(Payment payment) {

        // Save the payment to the database

    }

}

```

The `PaymentProcessor` class now has a single responsibility: to process a payment. The `ReportGenerator` class now has a single responsibility: to generate a report for a payment.

### Liskov Substitution Principle

The Liskov Substitution Principle (LSP) states that if S is a subtype of T, then objects of type T may be replaced with objects of type S (i.e., an object of type T may be substituted with any object of a subtype S) without altering any of the desirable properties of the program (correctness, task performed, etc.).

#### Example

```java

class Rectangle {

    private int width;

    private int height;

    public int getWidth() {

        return width;

    }

    public void setWidth(int width) {

        this.width = width;

    }

    public int getHeight() {

        return height;

    }

    public void setHeight(int height) {

        this.height = height;

    }

    public int getArea() {

        return width * height;

    }

}

class Square extends Rectangle {

    public void setWidth(int width) {

        super.setWidth(width);

        super.setHeight(width);

    }

    public void setHeight(int height) {

        super.setWidth(height);

        super.setHeight(height);

    }

}

```

In the above example, the `Square` class violates the Liskov Substitution Principle. If we substitute a `Square` object for a `Rectangle` object, the program will behave incorrectly.

### Interface Segregation Principle

The Interface Segregation Principle (ISP) states that no client should be forced to depend on methods it does not use.

#### Example

```java

interface PaymentProcessor {

    public void charge(Payment payment);

    public String createReport(Payment payment);

    public void printReport(String report);

    public void savePayment(Payment payment);

}

```

In the above example, the `PaymentProcessor` interface violates the Interface Segregation Principle. If we have a class that only needs to charge a payment, it will have to implement the `createReport`, `printReport` and `savePayment` methods, even though it does not need them.

Using the Interface Segregation Principle, we can refactor the `PaymentProcessor` interface into two interfaces, each with a single responsibility:

```java

interface PaymentProcessor {

    public void charge(Payment payment);

}

interface PaymentReport {

    public String createReport(Payment payment);

    public void printReport(String report);

}

interface SavePayment {

    public void savePayment(Payment payment);

}

```

The `PaymentProcessor` interface now has a single responsibility: to process a payment. The `PaymentReport` interface now has a single responsibility: to generate a report for a payment. The `SavePayment` interface now has a single responsibility: to save a payment to the database.

### Dependency Inversion Principle

The Dependency Inversion Principle (DIP) states that one should “Depend upon Abstractions. Do not depend upon concretions.

#### Example

You can check out an example [**here**](https://stackify.com/dependency-inversion-principle/)
