{book: true, sample: false}

# Chapter 10 - OOPs Concepts

#### What is OOPs?

Object Oriented Programming(OOPs) is a programming approach based upon objects and data. In OOP approach, we create templates known as classes and then create their runtime instances known as objects.


#### What is an object?

Object is a real life entity which has an identity and behaviour. Each object is an instance of a particular class or subclass with the class's own methods or procedures and data variables.

#### How can we create object of a class?

Once we define our class, we can create as many objects as we like of that class type. Following is an example of how to create object using new operator.

```php
$physics = new Books();
$maths = new Books();
$chemistry = new Books();
```

#### What is a class?

A class is a template that is used to create objects, and to define object data types and methods. Core properties include the data types and methods that may be used by the object. All class objects should have the basic class properties.

#### What are the basic features of OOPs?

1. Abstraction
2. Encapsulation
3. Polymorphism
4. Inheritance

#### Is PHP purely an object oriented language?

No, PHP is not purely object oriented. PHP supports object oriented approach as well as procedural approach.

#### Differentiate between OOPs & POPs.

| OOPs      | POPs           |
| ------------- |-------------|
| Takes bottom-up approach.      | Follows top-down approach |
| Program is divided into objects     | Program is divided into functions      |
| Each objects control it's own data | Here, data is global      |
| Data hiding and inheritance are available | No such features are there      |
| Java, C++ | Pascal, Fortran    |


#### What is generalization?

Generalization is the process of extracting shared characteristics from two or more classes, and combining them into a generalized superclass. Shared characteristics can be attributes, associations, or methods.

#### What is specialization?

Specialization is the reverse process of Generalization means creating new sub classes from an existing class.

#### What is aggregation?

Aggregation is a relationship between two classes that is best described as a "has-a" and "whole/part" relationship. It is a more specialized version of the association relationship. The aggregate class contains a reference to another class and is said to have ownership of that class.

#### What is composition?

Composition is a special case of aggregation. In other words, a restricted aggregation is called composition. When an object contains the other object and the contained object cannot exist without the other object, then it is called composition.

#### What is association?

The association relationship indicates that a class knows about, and holds a reference to, another class. Associations can be described as a "has-a" relationship.

#### What is abstraction?

An abstraction denotes the essential characteristics of an object that distinguish it from all other kinds of objects and thus provide crisply defined conceptual boundaries, relative to the perspective of the viewer.

#### What is encapsulation?

Encapsulation is the process of binding both attributes and methods together within a class. Through encapsulation, the internal details of a class can be hidden from outside. The class has methods that provide user interfaces by which the services provided by the class may be used.

#### What is inheritance?

Inheritance is a mechanism wherein a new class is derived from an existing class where a class inherits or acquires the properties and methods of other classes. 

#### What is super class?

The class from which it's derived is called the superclass.

#### What is a sub class?

The derived class (the class that is derived from another class) is called a subclass.

#### How can you inherit a class in PHP?

We declare a new class with additional keyword `extends`.

#### What is a constructor?

If a class name and function name will be similar in that case function is known as constructor.

Constructor is special type of method because its name is similar to class name.

Constructor automatically calls when object will be initializing.

#### Explain __construct().

By using this function we can define a constructor.

It is known as predefined constructor. Its better than user defined constructor because if we change class name then user defined constructor treated as normal method.

If predefined constructor and user defined constructor, both are defined in the same class, then predefined constructor will be treated as a Constructor while user defined constructor treated as normal method.

#### Classify constructor.

1. Default constructor
2. Parameterized constructor
3. Copy constructor

#### What is a destructor?

The Destructor method will be called as soon as there are no other references to a particular object, or in any order during the shutdown sequence.
 __destruct() is used to define destructor.

#### Explain $this.

To access or change a class method or property within the class itself, it’s necessary to prefix the corresponding method or property name with `$this` which refers to this class.

#### Explain multiple inheritance.

Multiple inheritance is a feature of some object-oriented computer programming languages in which an object or class can inherit characteristics and features from more than one parent object or parent class.

#### Does PHP support multiple inheritance?

No. PHP only supports multi-level inheritance.

#### Explain multi-level inheritance.

When a class is derived from a class which is also derived from another class, i.e. a class having more than one parent classes, such inheritance is called Multilevel Inheritance. The level of inheritance can be extended to any number of level depending upon the relation.

#### What is polymorphism?

The Greek word Poly means “many” and morph means property which help us to assign more than one property with a single name.
1. Method overloading 
2. Method overriding
These are the example of polymorphism.

#### What is method overloading?

Method overloading is the phenomenon of using same method name with different signature.

#### Does PHP support method overloading?

PHP doesn’t support method overloading concept.

#### What is method overriding?

Method definitions in child classes override definitions with the same name in parent classes. In a child class, we can modify the definition of a function inherited from parent class.

#### What are interfaces in PHP?

Interfaces are defined to provide a common function names to the implementors. Different implementors can implement those interfaces according to their requirements. You can say, interfaces are skeltons which are implemented by developers.

#### What does the presence of operator ‘::’ represent?

The scope resolution operator :: allows any declaration/definition of methods, variables outside the body of a class. 

#### How to define a class in PHP?

Class always start with `class` keyword. After this write class name without parentheses.

```php
class demo{
    function add() {   
        $x = 800;
        $y = 200;
        $sum = $x + $y;
        echo "sum of given no= ". $sum . "<br/>";	
    }
    function sub() {
        $x = 1000;
        $y = 200;
        $sub = $x - $y;
        echo "Sub of given no = " . $sub;	
    }
}
```


#### How will you add a constructor function to a PHP class?

PHP provides a special function called __construct() to define a constructor. You can pass as many as arguments you like into the constructor function.

#### How will you add a destructor function to a PHP class?

Like a constructor function you can define a destructor function using function __destruct(). You can release all the resourceses with-in a destructor.

#### How will you access the reference to same object within the object in PHP?

The variable $this is a special variable and it refers to the same object ie. itself.

#### What do you mean by access modifier?

Access Modifier allows you to alter the visibility of any class member(properties and method).
In php, there are three scopes for class members.
1. Public
2. Protected
3. Private

#### Explain access modifiers in PHP.

1. Public access modifier is open to use and access inside the class definition as well as outside the class definition.

2. Protected is only accessible within the class in which it is defined and its parent or inherited classes.

3. Private is only accessible within the class that defines it.( it can’t be access outside the class means in inherited class).

#### Explain final class in PHP.

The final keyword prevents child classes from overriding a method by prefixing the definition with final.

It means if we define a method with final then it prevent us to override the method.

#### Explain abstract class.

There must be a `abstract` keyword that must be return before this class for it to be abstract class to implement Abstraction.

This class cannot be instantiated. only the class that implement the methods of abstract class can be instantiated.

There can be more than one methods that can left undefined.

#### What is interface?

The class that is fully abstract is called interface.

Any class that implement this interface must use implements keyword and all the methods that are declared in the class must be defined here. otherwise this class also need to be defined as abstract.