# Description

Specify a pointer to the current object.

# Solution

Introduce the concept of an object - an instance of an abstract data type. Object protects its data and controls operations on its data.

# Examples

## ProceduralFunctional Programming

In procedural and functional programming you have a function that works based on parameters data and produces the result.

This concept is very old and is used in "C" language.

```C
int calculateIncomeTax(Employee emp);

typedef struct Employee {
    int salary;
    int sharesIncome;
} Employee;

int calculateIncomeTax(Employee emp) {
  int salary = emp.salary;
  int sharesIncom = emp.sharesIcome;
  
  // Calculate the tax based on the salary and shares income
  
  return result;
}

// Somewhere in code call the method,
// initialize Employee data
struct Employee emp;
emp.salary = 99999;
emp.sharesIncome = 11111;

// Call the method by sending to it our Employee structure:
int tax = calculateIncomeTax(emp);

```

In the same manner all core Functional Programming languages are working, like ML and Haskell.

### Object Oriented Programming

Object oriented languages introduced the conept of object. The function becomes the method, a function linked to the object.

```Java
// Java
class Employee {
   public String name;
   public int salary;
   public int sharesIncome;
  
   public int calculateIncomeTax() {
       // Calculate tax based on:
       this.salary 
       this.sharesIncome
     
       return result;
   }
}

// Somewhere in another class and method,
// create an instance of the class - object emp:
Employee emp = new Employee();
emp.salary = 999999;
emp.sharesIncome = 111111;

// Call the method in the object:
int tax = emp.calculateIncomeTax();
```


C++, Java, Scala, Kotlin, C#, JavaScrpt use keyword "this" to point to the current object.
The programming languages still use the old technic by passing the object to the function, though hiding it from programmers.

```Java
// The code behind the scene:
public int calculateIncomeTax(Employee this) {
     // Calculate tax based on:
     this.salary 
     this.sharesIncome

     return result;
 }
```

Python makes it more clear and requires explicit "self" keyword:
```Python
class Employee(): 
      
    # init method or constructor 
    def __init__(self, salary, sharesIncome): 
        self.salary = salary 
        self.salary = salary 
          
    def calculateIncomeTax(self): 
        // Calculate tax based on:
        self.salary 
        self.sharesIncome

        return result;
        
        
# Somewhere in the code
emp = Employee(99999, 11111)
tax = emp.calculateIncomeTax()
```
