---
layout: default
title: Built-In Arrays 
parent: Pointers
grand_parent: C++ 20
nav_order: 3
---
 
# Built-In Arrays

New applications generally should use *std::array* and *std::vector* to create safer, more robust applications. This objects always know their own size - even when passed to other functions.

### Declaring and Accessing a Built-In Array
```c++
int c[4];		// array of 4 integers

// built-in array with initializer list
int n[10]{1,2,3,4,5};	// remaining elements are value initialized with 0
int m[]{1,2,3,4,5};
``````

### Declaring Built-In Array Parameters
```c++
// prototype
int sumElement(const int values[], size_t numberOfElements);

// compiler converts const int values[] to const int *values
int sumElement(const int *values, size_t numberOfElements);
```