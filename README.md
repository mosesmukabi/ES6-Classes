# ES6 CLASSES

Classes are used to define the blueprint for real-world object modeling and organize the code into reusable and logical parts.  

In ES6, we can create the class by using the class keyword. We can include classes in our code either by class expression or by using a class declaration.   

## syntax of class expression

``` javascript
var Polygon = class { 
   constructor(height, width) { 
      this.height = height; 
      this.width = width; 
   } 
}
```

## Example

``` javascript
var Student = class{  
    constructor(name, age){  
    this.name = name;  
    this.age = age;  
    }  
}  
```

## syntax of class declaration

``` javascript
var Polygon = class { 
   constructor(height, width) { 
      this.height = height; 
      this.width = width; 
   } 
}
```

## Example

``` javascript
class Student{  
    constructor(name, age){  
    this.name = name;  
    this.age = age;  
    }  
  
} 
```
## Instantiating an Object from class
Like other object-oriented programming languages, we can instantiate an object from class by using the new keyword.

### Syntax
``` javascript
var obj_name = new class_name([arguements])  
```

### Example

``` javascript
var stu = new Student('Peter', 22) 
```
## Accessing functions
The object can access the attributes and functions of a class. We use the '.' dot notation (or period) for accessing the data members of the class.

### Syntax
``` javascript
obj.function_name();  
```

### Example

``` javascript
'use strict';
class Student {   
   constructor(name, age) {   
      this.n = name;   
      this.a = age;  
   }   
   stu() {   
      console.log("The Name of the student is: ", this.n)   
      console.log("The Age of the student is: ",this. a)   
   }   
}   
  
var stuObj = new Student('Peter',20);   
stuObj.stu();  
```
### Explanation
In the above example, we have declared a class Student. The constructor of the class contains two arguments name and age, respectively. The keyword 'this' refers to the current instance of the class. We can also say that the above constructor initializes two variables 'n' and 'a' along with the parameter values passed to the constructor.

The object stuObj is created by using the class Student. The object stuObj is then passed to the function stu() of the class Student.

The function stu() in the class will print the values of name and age.

### Output

``` javascript
The Name of the student is: Peter
The Age of the student is: 20
```
## The Static keyword
The static keyword is used for making the static functions in the class. Static functions are referenced only by using the class name.

### Example
``` javascript
class Example {   
   static show() {   
      console.log("Static Function")   
   }   
}   
Example.show() //invoke the static method  
```

### Output
``` javascript
Static Function
```
## Class inheritance
Classes can inherit attributes and methods from another class. This is done by using the extends keyword.  

efore the ES6, the implementation of inheritance required several steps. But ES6 simplified the implementation of inheritance by using the extends and super keyword.

Inheritance is the ability to create new entities from an existing one. The class that is extended for creating newer classes is referred to as superclass/parent class, while the newly created classes are called subclass/child class.

A class can be inherited from another class by using the 'extends' keyword. Except for the constructors from the parent class, child class inherits all properties and methods.

### Syntax
``` javascript
class child_class_name extends parent_class_name{  
}  
```
A class inherits from the other class by using the extends keyword.


### Example

``` javascript
'use strict';
class Student {   
   constructor(a) {   
    this.name = a;  
   }   
}   
class User extends Student {   
   show() {   
      console.log("The name of the student is:  "+this.name)   
   }   
}   
var obj = new User('Sahil');   
obj.show() 

```

### Output

``` javascript
The name of the student is:  Sahil
```

## Types of inheritance
Inheritance can be categorized as Single-level inheritance, Multiple inheritance, and Multi-level inheritance. Multiple inheritance is not supported in ES6.

## Single-level inheritance
It is defined as the inheritance in which a derived class can only be inherited from only one base class. It allows a derived class to inherit the behavior and properties of a base class, which enables the reusability of code as well as adding the new features to the existing code. It makes the code less repetitive.

``` javascript
'use strict';
class base_class
{
//code
};
class derived_class : public(access_modifier) base_class
{
//code
};
int main()
{
base_class object_1;
derived_class object_2;
//code
}
```

## Multi-level Inheritance
In Multi-level inheritance, a derived class is created from another derived class. Thus, a multi-level inheritance has more than one parent class.
 
``` javascript
'use strict';
class Animal{    
   eat(){  
      console.log("eating...");  
   }    
   }    
   class Dog extends Animal{    
    bark(){  
       console.log("barking...");  
   }    
   }    
   class BabyDog extends Dog{    
    weep(){  
       console.log("weeping...");  
      }    
   }    
   var d=new BabyDog();    
   d.eat();    
   d.bark();    
   d.weep();    
```

### Output

``` javascript
eating...
barking...
weeping...
```

## Method Overriding and Inheritance
It is a feature that allows a child class to provide a specific implementation of a method which has been already provided by one of its parent class.

#### There are some rules defined for method overriding -

The method name must be the same as in the parent class.
Method signatures must be the same as in the parent class.

### Example
``` javascript
'use strict';
class Parent {   
   show() {   
      console.log("It is the show() method from the parent class");  
   }  
}  
class Child extends Parent {   
   show() {   
      console.log("It is the show() method from the child class");  
   }   
}   
var obj = new Child();   
obj.show(); 
```
the implementation of the superclass function has changed in the child class. You will get the following output after the successful execution of the above code:

### Output

``` javascript
It is the show() method from the child class
```

## The super keyword
It allows the child class to invoke the properties, methods, and constructors of the immediate parent class.   
The ```super.prop and super[expr] ```expressions are readable in the definition of any method in both object literals and classes.

### Syntax
``` javascript
super(arguments);
```

### Example

``` javascript
'use strict';
class Parent {
   constructor() {  
      this.prop = 'parent';  
   }  
}  
class Child extends Parent {  
   constructor() {  
      super();  
      this.prop = 'child';  
   }  
}  
var obj = new Child();  
console.log(obj.prop);
}
```
### Explanation
In the above example, the super keyword is used to invoke the constructor of the parent class.

The object obj is created by using the class Child. The object obj is then passed to the constructor of the class Child.

### Output

``` javascript
child
```