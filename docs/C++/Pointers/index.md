---
layout: default
title: Pointers
nav_order: 3
has_children: true
parent: C++ 20
permalink: /docs/C++/Pointers
---
# Pointers in C++ 20

This page describes pointers, built-in pointer-based arrays and pointer-based strings.

Modern C++ has added featues that eliminate the need for most pointers. 

- using *std::array* and *std::vector* objects over using built-in pointer-based arrays 
- using *std::string* and *std::string_view* objects over pointer-bassd C-string

## Recommendation

Implementing pass-by-reference using references rather than pointers.

## Features for Avoiding Pointers
- *to-array* converts a pointer-based array to a *std::array*
- *spans* offer a safer way to pass built-in arrays to functions. 