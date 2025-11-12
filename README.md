# **Udacity C++ Nanodegree Program**

## **Skills You'll Learn**

### &emsp; **_Introduction to C++_**

A* search algorithm | Control flow | C++ syntax | C++ data structures | C++ file handling | C++ constants | Software
project organization | C++ user input | C++ header files | Cmake | C++ pointers | C++ data types

### &emsp; **_Object-Oriented Programming in C++_**

C++ polymorphism | Access specifiers | Encapsulation | Generic programming | C++ inheritance | Raii | Smart pointers
| C++ header files | C++ pointers | C++ standard library | C++ data structures | Classes in programming | Errors and
exceptions | Resource leaks | Stack memory | Intermediate object-oriented programming | Heap memory | Memory
leaks | Dynamic memory allocation | C++ classes | C++ copy and move semantics

### &emsp; **_Memory Management_**

Computer memory architecture | Dynamic memory allocation | C++ copy and move semantics | Heap memory | Memory
management in c++ | R-values | Smart pointers | Buffer overruns | Memory-efficient programming | Call-by-value | Rule
of three | Memory leaks | L-values | Code debugging | Segmentation fault | Automatic memory allocation | Hexadecimal
numbers | Variable scope | Call-by-reference | Rule of five | Memory fragmentation | Virtual memory | Stack memory
| Ownership in memory management | Uninitialized memory bugs | Call stacks | Raii

### &emsp; **_Concurrency_**

Threading | Concurrent computing | Futures and promises | Message queues | Parallel computing | Data races

## **Courses**

### &emsp; [**_01. Introduction to C++_**](./C2_CppFoundations/)

This course guides learners through the essentials of C++ programming. Starting with an overview and setup, students explore data structures using the Standard Template Library (STL), delving into functions and modular programming as well as Object-Oriented Programming (OOP). The course introduces fundamental algorithms through a hands-on search implementation, culminating in a practical project: building a Route Planner using OpenStreetMap. By the end, participants will be equipped with the skills to design and develop efficient C++ applications.

| **Lesson** | **Detail information** |
| :--- | :--- |
| 1. Welcome | Explore C++ with insights from its creator Bjarne Stroustrup, learn its industry impact, effective learning strategies, and key coding guidelines. |
| 2. Introduction to C++ and Setup | Get started with C++: learn program structure, compilation, data types, input/output, expressions, conditionals, loops, and user interaction through hands-on coding exercises. |
| 3. Working with Data Structures and STL | Learn to use arrays, vectors, and STL algorithms in C++ for data storage, string manipulation, file I/O, and efficient error handling to write robust, maintainable programs. |
| 4. Functions, Modularity and OOP | Master C++ modularity by organizing code with functions, multi-file structure, and OOP—using classes, pointers, scope, linkage, and object lifecycle features for scalable design. |
| 5. Introduction to Algorithms – A Search Implementation* | Learn to model search problems with graphs and grids, implement A* pathfinding in C++, use STL containers and lambdas, analyze complexity, and build projects with CMake. |
| 6. `Project:` Build an OpenStreetMap Route Planner | In this project, you will build a route planner that determines and visualizes the optimal path between two points using real-world map data from the OpenStreetMap project. |

### &emsp; [**_02. Object-Oriented Programming in C++_**](./C3_OOP/)

In this course, participants will explore fundamental OOP concepts and their applications. Starting with class design and encapsulation, the course progresses to inheritance and composition, helping students construct effective class hierarchies. Delving into advanced topics, the lessons cover polymorphism and templates, crucial for building flexible and reusable code. Additionally, learners will gain vital skills in error handling and debugging techniques through targeted exercises. The course culminates in a practical project where students will develop a comprehensive system monitoring tool, solidifying their knowledge and coding competency.
 
| **Lesson** | **Detail information** |
| :--- | :--- |
| 1. Encapsulation and Class Design | Master encapsulation in object-oriented programming. Explore encapsulation principles, class structure, data hiding, and utilize getters and setters for efficient class design. |
| 2. Inheritance, Composition, and Class Hierarchies | Learn C++ inheritance, composition, and class hierarchies: design clear, safe class structures using single/multiple inheritance, polymorphism, and the "is-a" vs. "has-a" approach. |
| 3. Polymorphism in Depth and Templates | Master C++ polymorphism and templates to build flexible, efficient, and type-safe designs using abstract classes, interfaces, runtime dispatch, and the power of the standard library. |
| 4. Error Handling Strategies and Debugging Techniques | Discover robust error handling in C++ with exceptions, return codes, and optionals, plus learn essential debugging, logging, assertions, and RAII for reliable, safe code. |
| 5. `Project:` Build a System Monitoring Tool | In this project, you will develop a simple system monitor program inspired by htop to track and display system metrics in real time. |

### &emsp; [**_03. Memory Management_**](./C4_MemoryManagement/)

This course provides a comprehensive exploration of how memory interacts with programming languages. Beginning with the fundamentals of system memory hierarchy, students learn essential concepts like pointers and pointer arithmetic. The course delves into dynamic memory allocation, highlighting ownership principles to manage memory effectively. Fundamental object-oriented topics such as copy constructors and move semantics are covered, addressing the crucial Rule of Three/Five for robust memory management. Additionally, advanced techniques involving smart pointers are introduced to enhance memory safety. The course culminates in a hands-on project to apply learned skills in real-world scenarios.

| **Lesson** | **Detail information** |
| :--- | :--- |
| 1. Memory Fundamentals and the System Memory Hierarchy | Explore C++ memory structure, pointers, addresses, the system memory hierarchy, caching, and GDB debugger use for efficient programming and troubleshooting. |
| 2. Pointers and Pointer Arithmetic | Learn C++ pointers: how they store memory addresses, enable direct data manipulation, perform pointer arithmetic, and avoid common errors like null, dangling, and out-of-bounds pointers. |
| 3. Dynamic Memory Allocation (Heap) and Ownership | Learn dynamic memory allocation in C++: using new/delete, preventing leaks, double deletion, and dangling pointers, and managing ownership with best practices and smart pointers. |
| 4. Copy Constructors, Move Semantics, and the Rule of Three/Five | Learn C++ copy constructors, move semantics, and the Rule of Three/Five. Master memory management, deep vs. shallow copy, and RAII for safe, efficient resource handling. |
| 5. Smart Pointers and Advanced Memory Management| Master C++ smart pointers for safer, modern memory management: exclusive and shared ownership, avoiding leaks, breaking cycles, and refactoring legacy code using unique, shared, and weak pointers. |
| 6. `Project:` Memory BOT | In this project, you will build a simple, terminal-based chatbot that creates a dialogue where users can ask questions about some aspects of memory management in C++ via a terminal.  |

### &emsp; [**_04. Concurrency_**](./C5_Concurrency/)

This course provides a comprehensive introduction to concurrent programming concepts. It begins with an exploration of threads and parallel execution, focusing on how tasks can run simultaneously to enhance performance. The course then delves into critical aspects of shared data management and task synchronization, ensuring that multiple threads can operate without conflict. Students will learn about essential tools such as mutexes, locks, and condition variables, which are crucial for managing access to shared resources safely. Finally, participants will apply their knowledge in a project that integrates all learned concepts, fostering practical experience in designing and implementing concurrent systems.


| **Lesson** | **Detail information** |
| :--- | :--- |
| 1. Threads and Parallel Execution  | Learn how to create, manage, and synchronize threads in C++ to unlock parallel execution, avoid race conditions, and ensure safe resource management using RAII and synchronization primitives. |
| 2. Threads: Sharing Data and Task Synchronization | Master thread communication and synchronization using promises, futures, std::async, atomics, and lock-free programming for scalable, efficient concurrent applications. |
| 3. Mutexes, Locks, and Condition Variables | Master advanced thread synchronization with mutexes, locks, and condition variables to build correct, efficient, and deadlock-free concurrent systems using modern C++ techniques |
| 4. `Project:` Program a Concurrent Traffic Simulation | In this project, students will create a multithreaded traffic simulation where vehicles navigate intersections safely by using mutexes and synchronization to prevent collisions. |