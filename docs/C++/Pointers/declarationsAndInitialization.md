---
layout: default
title: Declarations and Initialization
parent: Pointers
grand_parent: C++ 20
nav_order: 3
---

# Pointer Variable Declarations and Initialization

Pointer variable contain memory address as their values. In this sense, a variable name **directly references a value** and a pointer **indirectly references a value**.

```c++
// declaring pointer
int *countPtr{nullptr};	// use nullptr rather than 0 or NULL
```

### Address Ooperator
```c++
// declare variable
int y{5};	

// declare ptr			
int *yPtr {nullptr};

// assign address of y to ptr	
yPtr = &y;				
```

### Indirection Operator or Dereferencing Operator
```c++
std::cout << *yPtr << std::endl;

std::cout << y << std::endl;
```