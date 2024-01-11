---
layout: default
title: Relationship Between Base and Derived Classes
parent: Inheritance
grand_parent: C++ 20
nav_order: 3
---

# Inheritance
The **colon(:)** indicates inheritance, and *public* to its right specifies the kind of inheritance. In *public* inheritance, *public* base-class members remain *public* in the derived class and *protected* ones remain *protected*.

Although the class source code does not contain these inherited members, they're nevertheless a part of a class. 

## A Derived-Class Constructor Must Call Its Base Class's Constructor
Each derived-class constructor must call a base-class constructor. We do this explicitly via a **base-class initializer** - a member initializer that passes arguments to a base-class construct.

A derived-class constructor must call its base class's constructor with any required arguments. This ensures that inherited *private* base-class members, which the derived class cannot access directly get initialized. 

The compiler would issue an error if the Derived-Class constructor did not explicitly invoke Base-Class constructor. If the Base-Class provides a default constructor, the derived-class constructor can call the base-class constructor implicitly.

To call redefined base-call member function from the derived class, place the base-class name and the scope resolution operator (::) before the base-class member-function name. Base-Class:: is required here to avoid infinite recursion. 
Each base-class constructor initializes the base-class data members that its derived classes inherit.

## Relationship Among Objects in an Inheritance Hierarchy

Assign derived-class object address to a base-class pointer ist allowed because a derived-class object is *an* object of its base class. 
Even though the base-class pointer points to a derived-class object, the base class member function is invoked. The invoked function depends on the pointer type (or reference type) used to invoke the function, not the object type for which the member function is called. 

The compiler allows us to invoke only base-class member functions via a base-class pointer. 

## virtual Functions in the Hierarchy

If we aim a base-class pointer at a derived-class object and use that pointer to call a function, the derived class object's function will be invoked polymorphically. 
Declaring the member function *virtual* and invoking it through a base-class pointer or reference causes the program to determine at execution time which function to invoke based on the object's type

Declaring functions using the **override** keyword tells the compiler to check whether the base class has a *virtual* member function with the same signature. If not, the compiler generates an error. This ensures that you override the appropriate base-class function. It also prevents you from accidentally hiding a base-class function with the same name but a different signature. Apply *override* to the prototype of every derived-class function that overrides a *virtual* base-class function. 

- **virtual** specifically introduces a new *virtual* function in a hierarchy.
- **override** specifically indicates that a derived-class function overrides a base-class *virtual* function.