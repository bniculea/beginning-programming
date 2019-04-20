# Session 5

### Complicated expression

- We can get to more complicated expression by combining multiple operators
    - Example:
        - `2 * (3 + 3 * (5 + 4))`
        - The normal rules for operator precedence apply, so multiplication and division happen before adition or subtraction
        - The steps for solving the previous operation are:
            - We first evaluate the expression `5 + 4` (9)
            - Then we multiply with `3` (27)
            - We add the result to `3` (30)
            - In the last stept we multiply the previous result with `2` and get `60`
        - If you are not sure about how your expression will be evaluated then use parantheses to produce the result you want.

### Range limits for various data types

- Sometimes it is useful to determine within a program exactly what the limits are on the values that can be stored by a given type (e.g int, float, double, etc).
- The `limits.h` header file defines symbols that represent values for the limits for each type
- The table below displays the symbols which represents range limits for integer types

    |Type         | Lower limit | Upper limit | 
    |-------------|-------------|-------------|
    |`char`       |`CHAR_MIN`   | `CHAR_MAX`  |
    |`short`      |`SHRT_MIN`   | `SHRT_MAX`  |
    |`int`        |`INT_MIN`    | `INT_MAX`   |
    |`long`       |`LONG_MIN`   | `LONG_MAX`  |
    |`long long`  |`LLONG_MIN`  | `LLONG_MAX` |

- The lower limits for the unsigned integer types are all `0`, so there are no symbols for these.
- The symbols corresponding to the upper limits for the unsigned integer types can be found in the table below:

    |Type                  | Upper limit | 
    |----------------------|-------------|
    |`unsigned char`       | `UCHAR_MAX`  |
    |`unsigned short`      | `USHRT_MAX`  |
    |`unsigned int`        | `UINT_MAX`   |
    |`unsigned long`       | `ULONG_MAX`  |
    |`unsigned long long`  | `ULLONG_MAX` |

- You could initialize a variable with the maximum possible value for type double like this:
    - `int number = INT_MAX`

- The `limits.h` header file  contains the range limits for the `integer` types. 
- In order to find the limits for the `floating` types, we have to include the `float.h` header file. 
- The limits for the `floating` types can be found in the table below:

    |Type         | Lower limit | Upper limit | 
    |-------------|-------------|-------------|
    |`float`       |`FLT_MIN`   | `FLT_MAX`   |
    |`double`      |`DBL_MIN`   | `DBL_MAX`   |
    |`long double` |`LDBL_MIN`  | `LDBL_MAX`  |

- The snippet below displays the values corresponding to the symbols defined in the header files: 

```c
#include <stdio.h>
#include <limits.h>
#include <float.h>


int main()
{
    printf("Variables of type char store values from %d to %d\n", CHAR_MIN, CHAR_MAX);
    printf("Variables of type unsigned char store values from 0 to %u\n", UCHAR_MAX);

    printf("Variables of type short store values from %d to %d\n", SHRT_MIN, SHRT_MAX);
    printf("Variables of type unsigned short store values from 0 to %u\n", USHRT_MAX);

    printf("Variables of type int store values from %d to %d\n", INT_MIN, INT_MAX);
    printf("Variables of type unsigned int store values from 0 to %u\n", UINT_MAX);

    printf("Variables of type long store values from %ld to %ld\n", LONG_MIN, LONG_MAX);
    printf("Variables of type unsigned long store values from 0 to %lu\n", ULONG_MAX);

    printf("Variables of type long long store values from %lld to %lld\n", LLONG_MIN, LLONG_MAX);
    printf("Variables of type unsigned long long store values from 0 to %llu\n", ULLONG_MAX);

    printf("\nThe size of the smallest positive non-zero value of type float is %.3e\n", FLT_MIN);
    printf("The size of the largest value of type float is %.3e\n", FLT_MAX);

    printf("The size of the smallest non-zero value of type double is %.3e\n", DBL_MIN);
    printf("The size of the largest value of type double is %.3e\n", DBL_MAX);

    printf("The size of the smallest non-zero value of type long double is %.3Le\n", LDBL_MIN);
    printf("The size of the largest value of type long double is %.3Le\n", LDBL_MAX);

    return 0;
}

```

### The sizeof operator

- You can find out how many bytes are occupied by a given type by using the `sizeof` operator.
- The expression `sizeof(int)` will result in the number of bytes occupied  by a variable of type int, and the result is an integer of type `size_t`
- Type `size_t` is defined in the standard header file `stddef.h` (also in some other headers) but best practice is to use the one from the `stddef.h` library.
- Example of storing a value that results from applying the `sizeof` operator:
    - `size_t size = sizeof(long long);`


### Choosing the correct type for the job

- When we decided what type to use for storing a specific value,  we have to take into account the fact that it accomodates the range of values.
- If we are storing a value close to the highest possible value and then we make certain operation(s) which will increase the value, there is a high possiblity that we will obtain a negative value.
    - The reason behind this is that once a value is outside the range, it will start counting again from the other range limit

- The snippet below will prove the point:

    ```c
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        short januarySalary = 23500;
        short februarySalary = 19300;
        short marchSalary = 21600;

        short quarterSalary = januarySalary + februarySalary + marchSalary;

        printf("Quarter salary: %d", quarterSalary);

        return 0;
    }

    ```
    - Here are are allocating three variable of type short, which will hold the salary for January, February and March
    - As you remember, the maximum value which the `short` type can hold is `32767`
    - If we add `23500` with `19300` and `21600` we obtain `64400`
    - When we run, we will obtain a negative value and that's because we are exceeding the maximum value which can be hold by the `short` type and we start to count from the lower limit (which is `-32768`)

### Char type

- A variable of type char can store the code for a single character
- Because it sotres a character code, which is an integer, it's considered to be an integer type
    - Due to this, you can treat a char value just like any other integer so you can use it in arithmetic calculations
- The integer value that's stored in a variable of type char, require just `1 byte` of memory.
- An `unsigned char` can have values between `0 and 255`
- As a signed type, a variable of type `char` can store values from `-128 to -127`
- You can specify the value for a variable of type `char` by using a __character constant__.
- A __character constant__ can be just a character written between single quotes.
- Example of `char` variables:
    - `char letter = 'A'`
    - `char digit = 9`
    - `char exclamation='!'`
 TODO => Add example of displaying a word and also a similar exercise. Use asciitable.com
### Exercises

1. Use parantheses  so  that the the following expression evaluates to `18`
    - `2 + 8 * 12 / 4 + 2`
2. Create a program which will display how many bytes the following types occupy:
    - char, short, int, float, double
    - The output should look like this:
        - Variables of type char occupy 1 bytes.
    - HINT: make use of the `sizeof` operator