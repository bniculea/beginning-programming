## Topics to be discussed in the second session

### 1. Functions
- A function defines a certain task that we want to accomplish: e.g compute the perfect square of a number, display a hello world message, display a person's full name, etc.
- When defining a function, we will use the following template:
    - ```c
        <return type> <function name> (<list of parameters>){
            <body-of-the-function>
        }
    ```
- __<return type>__  - refers to the value which is returned by the function. This can be either **int** or **void** (in a future lesson we will learn that there are multiple types, other than **int**) 
    - A function can return one or zero values
    - If it returns a value, it has to  specify the type of the returned value. This means that the function should return, for example, an integer number (e.g 5, 11, 2123, etc)
    - If it does not return a value, we should use the keyword **void** before declaring the function name
- __<function name>__ - represents the names that we gave to that piece of code which is handling a specific task for us. This is useful when we want, later, to call the function. Calling a function is like a shortcut, we just want to bring some functionality into our logic but without recreating it, maybe it was not even created by us. For example, we are using the **printf** function but this is a piece of code which is not created by us.
- <list of parameters> - represents the input data which is used by our function in order to fulfill its responsibilities. We can think to a function like to a cookie:
    - the parameters are the ingredients to our recipe (e.g sugar, milk, etc)
    - the recipe is the logic which mixes in the ingredients (a.k.a parameters)
    - the cookie is the end result of our function when it is called
- With the except of the main function, every function has to be defined before it is used
    - When we define a function, we only need to specify its return type, name and the list of parameters, for example:
        - void displayAddress();
        - int computeDistance(int x, int y);


#### 1.1 Exercises
- Create a function named ***displayFirstName*** which displays  your name
- Repeat the previous exercise only that now pass the name as a parameter
- Create a function which takes as input the width and the height of a rectangle and displays it.
- Repeat the previous exercises only that know, the function should return the value instead of displaying it

### 2. Comments
- Are a piece of text ignored by the compiler
- Comments can be on one line or multiple lines

#### 2.1 Exercises
- Add comments to the hello world program to specifiy what each line does

###  3. Variables
- A variable is simply a container in which we can stuff values, characters or any kind of information
- Later we are using the name of the container as a placeholder for the value which is placed inside
- This container is named after what it holds (for example age)

    ```c
    // Create a variable called value, which is of type integer and has the value 0
    int val = 0;
    // Assign to the variable the result of the operation from the right hand side
    val = 3 + 5;
    // Create a new variable and as a value, use double the value which is hold in the val variable
    int doubledValue = value * 2;
    //We can declare variables without initializing them
    int unusedVariable;
    ```
### 4.Increment/Decrement operators

#### 4.1 Increment operators
- In C, the Increment operator is represented by ___++__ operators in front of a variable or after the variable.
- The effect of this operator is that it will increase the value present in the variable with 1.
- For example, ++a it is a syntactic sugar for:
    - int a = a + 1;
- The position can be either sufix or prefix, but it can influence the end result:
    ```c
    int a = 0;
    printf("%d", ++a); // this displays 1 as the number is first incremented and afterwards displayed
    int b = 2;
    printf("%d", b++); // the value displayed is 2 because the number is first displayed and afterwards incremented. This means the when the b variable will be used for the next time, it will have a value of 3.
    ```

#### 4.2 Decrement operators
- Exactly the same with the increment operators only that the symbol is __--__ instead of __+__
- It is substracting 1 from the variable near which is placed
- For example --a t is syntactic sugar for:
    - int a = a-1;
- As for the increment operators, the position can be either sufix or prefix, but it can influence the end result:
    ```c
    int a = 0;
    printf("%d", ++a); // this displays 1 as the number is first incremented and afterwards displayed
    int b = 2;
    printf("%d", b++); // the value displayed is 2 because the number is first displayed and afterwards incremented. This means the when the b variable will be used for the next time, it will have a value of 3.
    ```
#### 4.3 Exercises
- What is the output of the program below:
    ```c
    int main()
    {
        int age = 18;
        printf("%d\n", ++age);
        int olderAge = age + 10;;
        printf("%d\n", olderAge)
    }
    ```


### 5. Homework exercises
1. What is the purpose of a function? How can it help a programmer?
2. Create a function which computes the area of a triangle. Give it all the parameters that it needs (base, height);
3. Create a function which transforms seconds into years, months and days
4. Create a function which accepts two integers from the user and calculates the sum of the two numbers. (You can choose either to return or display it)