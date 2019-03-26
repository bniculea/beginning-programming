# Session 4

### Variables and memory
-  Each time we declare a variable of a given type (e.g int), the compiler allocates sufficient space in memory to store values  specific to that particular type of variable
- Computer's memory is organized into bytes. Each variable will occupy some number of bytes in memory
- Variables of different types (e.g short, float, long, etc) may require different ammounts of memory to be allocated

---
### Integer types
---

#### Signed Integer types
- We have five basic types that we can use in order to store signed integer values.
- By signed we refer to positive and negative values
- Table with Signed Integer types: 
    
    |Type name    | Number of bytes |
    |-------------|-----------------|
    |`signed char`|       1         |
    |`short`      |       2         |
    |`int`        |       4         |
    |`long`       |       4         |
    |`long long`  |       8         |
- Some examples for variables of mentioned types:
    
    ```c
        short shoeSize;
        int houseNumber;
        long long starCount;
    ```
- Note: short, long, and long long can be written as:
    - `short int`
    - `long int`
    - `long long int`
    - However, these types are almost always written in thei abbreviated forms. Type int can also be written as `signed int`, but you won't see this often.

### Unsigned Integer Types

- Some kinds opf data are always positive
    - number of children in a class
    - a man's age
- For each type that stores signed integers, there is a corresponding type that stores unsigned integers
- The unsigned type occupies the same amount of memory as the signed type
- Each unsigned type name is essentially the signed type name prefixed with the keyword unsigned
- Table with unsigned integer types:
    
    |Type name            | Number of bytes |
    |---------------------|-----------------|
    |`unsigned char`      |       1         |
    |`unsigned short`     |       2         |
    |`unsigned int`       |       4         |
    |`unsigned long`      |       4         |
    |`unsigned long long` |       8         |
- Occupying the same number of bytes, the number of different values that can be represented is fixed.
- Using an unsigned type doesn't provide more values than the corresponding signed type, but it does allow numbers to be represented that are twice the magnitude
    - For example, signed char can represent values between -128 and 127 while unsigned char can occupy values between 0 and 255. 
- Example of unsigned integer variable declarations:
    - `unsigned int count`
    - `unsigned long population`

---
### Floating point types
---

- Floating point numbers hold values that are written with a decimal point, so you can represent fractional as well as integral values
- Examples of floating-point numbers
    - `1.6`
    - `0.0000009`
    - `234234.434`
    - `100.0`
- Floating-point numbers are often expressed as decimal values multiplied by some power of 10, where the power of 10 is called the exponent.
- Example of expressing floating-point values:
    |Value      |   With an exponent            |
    |-----------|-------------------------------|
    |`1.6`      | `0.16 x 10`<sup>`1`<sup>      |
    |`0.00008`  | `8.0 x 10`<sup>`-5`<sup>      |
    |`7655.899` | `0.7655899 x 10`<sup>`4`<sup> |
    |`100.0`    | `1.0 x 10`<sup>`2`<sup>       |


#### Floating-Point Variables

- Floating-point variable types only store floating-point numbers
- There are three types fo floating point numbers:

    |Type name       | Number of bytes | Decimal Digits Precision |
    |----------------|-----------------|--------------------------|
    |   `float`      |       4         |          7               |
    |   `double`     |       8         |          15              |
    | `long double`  |      12         |          18              |
- Example of floating-point variables declaration:
    - `float radius`
    - `double biggest`
- Values of type float are known as single precision floating-point numbers.
- In order to specify that a number is of type float, we have to add `f` after its value:
    - `float area = 24.56f`;
- If a floating-point value does not have the `f` at the end, the compiler will interpret it as a value of type `double`

#### Conversion specifiers for Floating-Point Variables

##### Floating point exercises

1. Given a land of 25 square kilometers splitted into 12 equal smaller areas, what is the surface of each smaller area?

    ```c
    #include <stdio.h>

    int main()
    {
        float landArea = 25.0f;
        float numberOfSlices = 12;
        float sliceSurface = landArea / numberOfSlices;
        printf("If we split a land of 25 square km into 12 pieces, each piece will have %f square km", sliceSurface);
        return 0;
    }
    ```