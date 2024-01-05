---
layout: default
title: array 
parent: Containers
grand_parent: C++ 20
nav_order: 3
---

# arrays
Each array knows its own size, which you can get via its *size* member function. 

### Declaring arrays
```c++
// values is an array of 5 int values, not implicitly initialized to zero
std::array<int, 5> values;

// init elements of array values to 0
for (size_t i{0}; i < values.size() ; ++i) {
	values[i] = 0;
}

// braced initializer
std::array<int, 5> values2{1,2,3,4,5};

// class template argument deduction (CTAD)
std::array values3{1,2,3,4,5};

// initialize elements to 0
std::array<int, 5> values4{};

// set all elements of values3 to 0
values3 = {};

// output earch array element
for (size_t i{0}; i < values.size(); ++i) {
       std::cout << values[i] << std::endl;
}

/*
 * access elements via the at member-function
 * [] operator provides no automatic array bounds checking
 * at member-function performs bounds checking
 */
for (size_t i{0}; i < values.size(); ++i) {
       std::cout << values.at(i ) << std::endl;
}

std::array<int, 4> values{1,2,3,4};
try {
	values.at(6);
} catch (const std::out_of_range &e) {
	std::out_of_range std::cerr << e.what() << std::endl;
}
```