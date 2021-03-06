## Topics to be discussed in the first session

### What are computers and how do they work
- Computers are not smarter than us they are only faster
- Computers work by using the binary system
- Binary system has only two digits 0 and 1 which translates into
    - has voltage
    - does not have voltage

- Exercises 
    - transform from Decimal to Binary the following numbers
        - 16, 32, 47, 57, 64
    - transform from Binary to Decimal the following numbers
        - 1111, 100001, 101110, 111010, 1000010

### What is a programming language
- In order to communicate with a system one has to use a language close to what a machine knows
- Usually machines know a low level language so there is a need for a high level language => This is a programming language =English to Computer Understandable Language
- A programming language instructs a piece of hardware
- Source Code file -> .c extension
- What is an IDE
- How can we install an IDE
- Basic introduction to CodeBlocks Interface

### C Programming language
- Very short introduction
- Why is usefull
    - Specify the connection between C and other popular languages
- How programming works:
    - Write the source code
        - into a file with an extension .c
    - Compile the source code into object code
    - Link the object code with libraries to build a program
    - Run and test the program

### Compiling from English to Source code
- A compiler is the component responsible with the  transformation of english words into  something called object code
- Compiler is also responsible with special instructions called **preprocessor directives**
    - An example is: 
        ```C
        #include <stdio.h>
        ```
    - Locates the header file named stdio.h
    - Add the content of the header file to the source code
    - Build the result into the object code
- A compiler is also responsible with for checking:
    - common mistakes
    - missing items
    - other issuee
- The object code is placed into a file with the **.o** extension

### Linking in the C Library
- Takes code written by us and it links it with other libraries (C included) and generates the application specific to the OS

### Hello world explained
```C
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("Hello world!\n");
    return 0;
}

```
- First two lines takes the code written by others and import it in our source code
    - For example, the function for displaying a set of characters is written by the creators of C
    - A text can be:
        - A character: 'a', 'b', 'c'
        - A String: "ana are mere"

- **main()**
    - is the name of the main function namely the one responsible with app start
- A function is a piece of code which makes a certain operation or operations
- A function can return one result or nothing
- The **int** specifies that the main function returns an integer number
- The **printf** is another function which has the role of displaying a text
- the last line specifies the integer number which is returned by the main function
- Usually the return number of main function specifies how the program ended:
    - 0 -> everything ok
    - -1 -> Something very bad happened
- This is because the OS requires any app to return something, like a proper goodbye
- What a function does is enclosed between {} paranthesis
- This is also called the scope
- **Every statement should end with a ; otherwise we get an error**

#### Exercises
- 1. Modify the program to display your name
- 2. Modify the program to also display your address

### Homework exercises:

#### 1. H1-Part1
1. Convert from decimal to binary the following numbers:
    - 29, 33, 19, 89, 55
2. Convert from binary to decimal the following numbers:
    - 101110, 101001, 11101, 111000, 1000100
3. Create a program which displays your name, address and age using a different printf for each statement
4. Repeat exercises 3 only that you have to use only one printf function
5. Create a program which displays the following figure
        
        ```C
        **********
        *        *
        **********
        ```
6. Create a program which displays the following triangle
```C
     *     
    * *
   *   *
  *     *
 *********
```
#### 2. H1-Part 2
1. Convert from decimal to binary the following numbers:
    - 123, 231, 245, 255
2. Convert from binary to decimal the following numbers:
    - 100000001, 101010101, 111100000
3. Create a program which displays the perfect square of the first 10 numbers (perfect square = patratul perfect al unui numar. De exemplu patratul perfect al numarului 8 este 64 deoarece 8x8 = 64). The program should print each perfect square on a single line like:
Square root of 1 is: 1
Square root of 2 is: 4
Square root of 3 is: 9
Square root of 4 is: 16

4. Create a program which will display the following figure:
```c
    * 
   * *
  * * *
 * * * *
* * * * *
* * * * *
 * * * *
  * * * 
   * *  
    *  
```