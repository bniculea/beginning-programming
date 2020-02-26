# Session 7

## Loops

- Loop means to repeat certain operation until a condition is met
- The number of steps that should be performed should be known otherwise an error will be thrown (Stack Overflow).
- Until we go straight into the loops theory we should remind about the:
    - increment operator
        - ```++```
        - e.g `a++` is the same as `a+=1` or `a=a+1`
        - keep in mind that there is a difference between `++a` and `a++`
            - eg:
                ```c
                    int a = 10;
                    int b = 11;
                    cout << ++a; // this prints 11
                    cout << b++; // this prints 11
                    cout << b; // now b is 12
                ```
            - always keep in mind that if the operator comes in front of the variable then you do that operation and afterwards the rest
    - decrement operator
        - ```--```
        - e.g `a--` is the same as `a-=1` or `a=a-1`
        - keep in mind that there is a difference between `--a` and `a--`
            - eg:
                ```c
                    int a = 10;
                    int b = 11;
                    cout << --a; // this prints 9
                    cout << b--; // this prints 11
                    cout << b; // now b is 10
                ```
            - always keep in mind that if the operator comes in front of the variable then you do that operation and afterwards the rest

## The `for loop`

- We typically use the for loop to execute a block of statements a given number of times. 
    - Let's suppose you want to display the numbers from 1 to 10. Instead of writing ten statements that coul `cout`, we can write it like this:
        - ```c++
            for (int count = 1; cout <=10; count++) {
                cout << count << " ";
            }
        ```
- The basic syntax of a for loop is:
    - ```c
        for(init_var;condition;increment_var){
            //run the action
        }
        ```
    - note:
        - `init_var` - this is the part which executes only once, at the begginning of the loop.
            - it is used for initializing the counter, a.k.a the number which determines how many time the loop should run
        - `condition` - this is the part which is evaluated at the begginning of each loop
            - if it evaluates to `true` then the loop continues
            - if it evaluates to `false` then the loop ends
        - `increment_var` - this is the part which runs at the end of each cycle
            - it should increment the counter
    - Example: 
        - Compute the sum of numbers from 1 to 100:
            - ```c
                int sum = 0
                for(int i = 1; i <=100;i++){
                    sum += i;
                }
                cout <<"Sum is: " << sum;
            ```
        - Keep in mind the following:
            - the expression `int i = 1` is executed only once
                - `i` is available only inside the `for loop`
                - if we attempt to reference the `i` after we exit the loop, the code will not compile
            - The expression `i <= 100` will be checked at each iteration
                - an `iteration` is simply one execution of a loop scope
                    - if, for example, our  `for loop` runs for 10 times, we say that we had `10 iterations`
                - in a loop, the second expression must always be one which should evaluate to either `true` or `false`
            - The expression `i++` is executed after each `sum+=i`.
            - Also very important, keep in mind that each expression in the header of a for loop should be preceded by a semicolon (`;`):
                - for(exp1`;`exp2`;`exp3)
- In a `for` loop, we can omit completely the first statement which will initialize some counter, as long as this counter is initialized before the `for` loop. See the snippet below:
    - ```c
        int count = 1;
        for (;count <=10;count++){
            cout<<count;
        }
        cout << "after the loop, count has the value " << count;
        ```

    - We should observe the following:
        - even if the counter is initialized outside, we still use the `;` separator as before
        - unlike what we have seen before, when the `i` variable was not available outside the `for` loop, the `count` variable is still visible even outside the loop because was declared outside of the `for lop`
    - Below we can see a logical diagram which describes the flow of the program:
    -  ![Quadrants](../images/FOR-LOOP-DIAGRAM.png)

- Exercise 1: write a C++ program which draws the following box:
    ```c
        ********************
        *                  *
        *                  *
        *                  *
        *                  *
        *                  *
        *                  *
        *                  *
        *                  *
        *                  *
        *                  *
        ********************
    ```
    - Solution:
        - ```c++
            #include <iostream>

            using namespace std;

            int main()
            {
                cout << "********************";
                for (int i = 0; i < 12; i++){
                    cout<< "\n*                  *";
                }
                cout << "\n********************" <<endl;
            }
        ```


## TODO: Add more exercises with loops