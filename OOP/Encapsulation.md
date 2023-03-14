# Encapsulation

## What is Encapsulation?

**Encapsulation** is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as **data hiding**.

## How to use Encapsulation?

To use encapsulation, you must declare the variables of a class as private and provide public setter and getter methods to modify and view the variables values.

```java
public class Encapsulation {
    private String name;
    private int age;
    private int idNum;
    private String department;

    public int getIdNum() {
        return idNum;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public String getDepartment() {
        return department;
    }

    public void setIdNum(int newId) {
        idNum = newId;
    }

    public void setName(String newName) {
        name = newName;
    }

    public void setAge(int newAge) {
        age = newAge;
    }

    public void setDepartment(String newDepartment) {
        department = newDepartment;
    }
}
```

## Rules for Encapsulation

- The variables of a class must be declared as private.
- Provide public setter and getter methods to modify and view the variables values.
- The variables of a class can be declared as final (constant). If it is final, then it can be initialized only once, either via a default initializer or via an instance initializer or constructor.
- The variables of a class can be declared as static. If it is static, then a single copy of variable is created and shared among all the instances of the class.
- The variables of a class can be declared as transient. If it is transient, then it is not part of the object's persistent state.

## Encapsulation vs [Abstraction](Abstraction.md#abstraction)

| Encapsulation                                                                                                                  | Abstraction                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Encapsulation is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. | Abstraction is a process of hiding the implementation details and showing only functionality to the user. |
| Encapsulation is also known as data hiding.                                                                                    | Abstraction is also known as interface hiding.                                                            |
| Encapsulation is used to achieve data hiding.                                                                                  | Abstraction is used to achieve interface hiding.                                                          |
| Encapsulation is used to hide the values of a variable.                                                                        | Abstraction is used to hide the implementation details of a method.                                       |
| Encapsulation is used to restrict direct access to variables and methods.                                                      | Abstraction is used to restrict direct access to implementation details.                                  |

[**Go back**](README.md#oop)
