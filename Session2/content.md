## Topics to be discussed in the second session

### Functions
- A function defines a certain task that we want to accomplish: e.g compute the perfect square of a number, display a hello world message, display the full name, etc.
- When defining a function, we will use the following template:
    - ```c
        <return type> <function name> (<list of parameters>){
            <body-of-the-function>
        }
    ```
- __<return type>__  - refers to the value which is returned by the function this can be either **int** or **void** (in a future lesson we will learn that there are multiple types, other than **int**) 
    - A function can return one or zero values
    - If it returns a value, it has to  specify the type of the returned value. This means that the function should return, for example, an integer number (e.g 5, 11, 2123, etc)
    - If it does not return a value, we should use the keyword **void** before declaring the function name
- __<function name>__ - represents the names that we gave to that piece of code which is handling a specific task for us. This is useful when we want, later, to call the function. Calling a function is like a shortcut, we just want to bring some functionality into our logic but without redeclaring it. For example, we are using the printf function but
- With the except of the main function, every function has to be defined before it is used


#### Exercises
- 1. Create a function which displays  your name
- 2. Create a function which displays your address

### Comments
- Are a piece of text ignored by the compiler
- Comments can be on one line or multiple lines

#### Exercises
- Add comments to the hello world program to specifiy what each line does

###  Variables and operators
- A variable is simply a container in which we can stuff values, characters or any kind of information
- Later we are using the name of the container as a placeholder for the value inside
- This container is named after what it holds (for example age)

