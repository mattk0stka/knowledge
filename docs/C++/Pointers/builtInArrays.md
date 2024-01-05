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
### Passing Built-In Arrays to Functions
The value of a built-in array's name is implicitly convertible to a const or non-const pointer to the built-in array's first element- this is known as **decaying to a pointer**. The array name `n` is implicitly convertible to `&n[0]`. You don't need to take a build-in array's address to pass it to a function. 


### Declaring Built-In Array Parameters
```c++
// prototype
int sumElement(const int values[], size_t numberOfElements);

// compiler converts const int values[] to const int *values
int sumElement(const int *values, size_t numberOfElements);
```

### *to_array* to Convert a Built-in Array to a *std::array*
You should prefer *std::arrays* and *std::vectors* because they're safer, and they don't become pointers when you pass them to functions. `std::to_array` function makes it convenient to create a *std::array* from a built-in array.

```c++
const int values[]{1,2,3,4};
// creating a std::array from a built-in array
const auto array{std::to_array(values)};

// creating a std::array from an initializer list
const auto array2{std::to_array({1,2,3,4})};
```