# **C ++**
C++ is a general-purpose programming language that was developed as an enhancement of the C language to include object-oriented paradigm. It is an imperative and a compiled language. 
## Why Learn C++?
- C++ is one of the most used and popular programming languages.
- C++ is used in making operating systems, embedded systems, and Graphical User Interfaces.
- It is an object-oriented programming language that implements all the OOPs concepts such as **Abstraction**, **Encapsulation**, and **Inheritance**, which gives a clear structure to programs and allows code to be reused, lowering development costs and providing security.
- It is portable and can be used to create applications that can be adapted to multiple platforms.
- C++ is easy to learn so that you can choose it as your first programming language.
- It makes programming easy for programmers to switch to C++ because its syntax is similar to C, Java, and C#.

## Features
- C++ is a high-level, general-purpose programming language designed for system and application programming. It was developed by Bjarne Stroustrup at Bell Labs in 1983 as an extension of the C programming language.
- One of the key features of C++ is its ability to support low-level, system-level programming, making it suitable for developing operating systems, device drivers, and other system software.
- C++ has a large, active community of developers and users, and a wealth of resources and tools available for learning and using the language. Some of the key features of C++ include:
- Object-Oriented Programming: C++ supports object-oriented programming, allowing developers to create classes and objects and to define methods and properties for these objects.
- Templates: C++ templates allow developers to write generic code that can work with any data type, making it easier to write reusable and flexible code.
- Standard Template Library (STL): The STL provides a wide range of containers and algorithms for working with data, making it easier to write efficient and effective code.
- Exception Handling: C++ provides robust exception handling capabilities, making it easier to write code that can handle errors and unexpected situations.

![image](https://github.com/Shantanu2911/Notes/assets/143939657/bd03ca38-c069-4ca1-8067-711acd4924ac)

## Advantages of C++ :
- Simple
- Machine Independent (Platform dependant)
- Mid-level language
- Rich library support
- Speed of execution
- Case-sensitive
- Dynamic Memory Allocation
- Memory Management
- Multi-threading
- Pointer and direct memory-access
- Object oriented
- Compiled Language

## Disadvantages of C++ :
- Steep Learning Curve
- Verbose Syntax
- Error-Prone

![image](https://github.com/Shantanu2911/Notes/assets/143939657/65c3f32f-cedb-446e-8e48-afb79d38bf7c)

## INSTALLATION
![image](https://github.com/Shantanu2911/Notes/assets/143939657/6f4b7cbb-dbbd-4a1a-92ea-4371567cc15a)

## First-Code in C++

```
// C++ Program to display "Hello, World!"
#include <iostream>
using namespace std;

int main()
{
   cout << "Hello, World!";

   return 0;
}

```
### **Output**

![image](https://github.com/Shantanu2911/Notes/assets/143939657/e399a4c4-f3f2-4609-a937-72a05ef4294d)

- **// C++ program to display “Hello World”** : This line is a comment line.
- **#include** : This is a preprocessor directive. #include<iostream> tells the compiler to include the standard iostream file which contains declarations of all the standard input/output library functions
- **using namespace std** : This is used to import the entity of the std namespace into the current namespace of the program. The statement using namespace std is generally considered a bad practice. When we import a namespace we are essentially pulling all type definitions into the current scope.The std namespace is huge. The alternative to this statement is to specify the namespace to which the identifier belongs using the scope operator(::) each time we declare a type. For example, std::cout.
- **int main() { }** : A function is a group of statements that are designed to perform a specific task. The main() function is the entry point of every C++ program, no matter where the function is located in the program.
- **cout<<“Hello World”;** : std::cout is an instance of the std::ostream class, that is used to display output on the screen. Everything followed by the character << in double quotes ” ” is displayed on the output device. The semi-colon character at the end of the statement is used to indicate that the statement is ending there.
- **return 0** : This statement is used to return a value from a function and indicates the finishing of a function. This statement is basically used in functions to return the results of the operations performed by a function.
- **Indentation** : We must always use indentations and comments to make the code more readable. 

## Basic of Syntax

![image](https://github.com/Shantanu2911/Notes/assets/143939657/646728ca-157c-4539-a75d-df6d015c7d6c)

- __Header File__ : The header files contain the definition of the functions and macros we are using in our program. They are defined on the top of the C++ program.

  Syntax :
  ```
  #include <library_name>
  ```

- **Namespace** : A namespace in C++ is used to provide a scope or a region where we define identifiers. It is used to avoid name conflicts between two identifiers as only unique names can be used as identifiers.

  Syntax :
  ```
  using namespace std;
  ```

- **Main Function** : The main function is the most important part of any C++ program. The program execution always starts from the main function. All the other functions are called from the main function. In C++, the main function is required to return some value indicating the execution status.

  Syntax :
  ```
  int main() {

    ... code ....
    return 0;
  }
  ```
- **Blocks** :  Blocks are the group of statements that are enclosed within { } braces. They define the scope of the identifiers and are generally used to enclose the body of functions and control statements.

  Syntax :
  ```
  {
      
  // Body of the Function
  
    return 0;
  }
  ```
  
 - **Semicolons** : It is used to terminate each line of the statement of the program. When the compiler sees this semicolon, it terminates the operation of that line and moves to the next line.

  Syntax :
  ```
 any_statement ;
  ```
## __DATATYPES__ :
- **PRIMITIVE**
    - __Integer__
        - Size - 4 bytes 
        - Eg : 1, 4, 100
        - Range [unsigned] (0 to 2<sup>32</sup> - 1)
        - Range [signed] (- 2<sup>31</sup> to 2<sup>31</sup> - 1) (using MSB(mosy significant bit) as sign)
          
          ![image](https://github.com/Shantanu2911/Notes/assets/143939657/358d8de3-0f2f-4f39-8b26-9be26616beb6)
          ![image](https://github.com/Shantanu2911/Notes/assets/143939657/0248531d-fcc0-43ee-a284-d9ddda62226d)

    - __Float__       Eg : 3.14, 6.5, 1.00
       -   Size - 4 byte
       -   __DOUBLE__ - Size 8 byte
          ![image](https://github.com/Shantanu2911/Notes/assets/143939657/69f0e715-270b-43c2-bffb-b4dc92291380)

    - __Character__
       - Size - 1 byte
       - Eg : c, f, @, %
         
           ![image](https://github.com/Shantanu2911/Notes/assets/143939657/bd17c299-bc10-42ee-a2d9-a70d3786623c)

    - __Booleam__
        - Eg : 0, 1
        - Size 1 byte

          ![image](https://github.com/Shantanu2911/Notes/assets/143939657/baed3ee7-47b3-43df-a7bd-6f8bf875660a)

_LETS TRY IT OUT :_
   ![image](https://github.com/Shantanu2911/Notes/assets/143939657/426f59b3-2445-451d-9700-8d4804971ced)
_OUTPUT :_
   ![image](https://github.com/Shantanu2911/Notes/assets/143939657/271745ec-f365-4ed5-a8da-f4a069b5344f)

### Type Modifiers : 
![image](https://github.com/Shantanu2911/Notes/assets/143939657/36df7c42-8f54-4e42-942d-4c6c0aea19ca)

- **DERIVED**
    - Function
    - Array
    - Pointer
    - Reference
- **USER-DEFINED**
    - Class
    - Structure
    - Union
    - Enum

## IF-ELSE Statement :
![image](https://github.com/Shantanu2911/Notes/assets/143939657/70ac596d-6a69-4cfb-a612-7383ff1c192d)

## LOOPS IN C++ :








