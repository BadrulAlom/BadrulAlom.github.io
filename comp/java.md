---
layout: default
---

# Java Quick Tips

The following are just snippets of things as I job my memory of java by going over some [tutorials](https://docs.oracle.com/javase/tutorial/getStarted/application/index.html).

## Basics
* Every application must contain a main method whose signature is: public static void main(String[] args)
* You can name the argument anything you want, but most programmers choose "args" or "argv".
* The main method is the entry point for your application and will subsequently invoke all the other methods required by your program.


## Interfaces
* Interfaces are just the methods of the class

## Packages
* A package is a namespace that organizes a set of related classes and interfaces. In other words the hierarchy under which that class falls.

## Vairables
* Local Variables are what'd you'd expect. Variables declared locally in methods. As such, local variables are only visible to the methods in which they are declared; they are not accessible from the rest of the class.
* Instance Variables (Non-Static Fields) are also known as instance variables because their values are unique to each instance of a class.
* Class Variables (Static Fields) are anay field declared with the static modifier; this tells the compiler that there is exactly one copy of this variable in existence, regardless of how many times the class has been instantiated. Additionally, the keyword final could be added to indicate that the valu of a variable will never change.
