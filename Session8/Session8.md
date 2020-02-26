# Arrays / Vectori (in romanian)

- You will often need to store many data values of a particular kind in your programs
    - For example we might want to keep track of the heights of our colleagues and then compute an average
- we can easily solve this kind of problem by creating as many variables as needed. For example, if we only have 5 colleagues we can create 5 variables as follows:
    ```c++
        int heightAndrei = 175;
        int heightBogdan = 172;
        int heightRoxana = 165;
        int heightMirela = 178;
        int heightIoana = 199;
    ```
- But as you might observer, this can become troublesome if we have more data that we want to store. 
    - What will happen if we want to save the height of our 40 colleagues? Should we define 40 variables? No way!
- In this lesson we will see how can we solve this problem using Arrays (Vectors)


## Introduction

- An array is a fixed number of data items that are all of the same type.
- The data items in an array are referred to as elements
- The folowing array declaration is similar to a declaration for a normal variable that contains a single value, except that you've placed a number between square brackets `[]` following the name:
    - ```c++
        long numbers[10];
      ```
    - The number between square brackets defines how many elements the array contains and is called the array dimension
    - Each of the data items stored in an array is accessed by the same name
        - In the previous statement the array name is `numbers`
    - You select a particular element by using an `index value` between square brackets following the array name
    - Index values are sequential integers that start from zero, and `0` is the index value for the first array element
        - In our example, the index values for the elements in the `numbers` array run from 0 to 9, so the index value 0 refers to the first element and the index value 9 refers to the last element
        - Therefore you access the elements in the `numbers` array as `numbers[0], numbers[1], numbers[2], etc...`
    - Always remember that index values start from `0` and not `1`. In our case, the third element can be accessed using `numbers[2]`, due to this rule of starting from `0`.
    - You can think of the index value for an array element as the offset from the first element:
        - The first element,  is the first elements thus the offset is 0
        - The second element is offset by 1 from the first element, thus we access it via `numbers[2]`
        - etc...
- We can also specify an index for an array element by an expression in the square brackets following the array name. The expression must result in an integer value that correspond to one of the possible index values.
    - For example you could write numbers `[i-2]`. If i is 3m this accesses `numbers[1]`, the second element in an array. 
    - The only constraint for using an expression when accessing an element is that it must produce an `integer` result, and the result must be a legal index value for the array
For a better understanding of arrays, we should start with a example. In the following snippet we will see how easy is to compute the average grade score for the students in a class.

- Class Exercise 1
    - Compute the average grade of students from a class with 7 students. Each grade should be read via the standard input.  The average should be computed using the basic arithmetic average formula.
    - Solution: 
        - ```c
            #include <iostream>

            using namespace std;
            int main() {

                int grade = 0;
                int numberOfStudents = 7;
                int sum = 0;
                float average = 0.0f;

                for (int i = 0; i < numberOfStudents; i++) {
                    cout << "Enter a grade:";
                    cin >> grade;
                    sum += grade;
                }
                average =  (float)sum / numberOfStudents;
                cout << "\nAverage of the grades from these 7 students is: " << average;

                return 0;
            }

            ```
    - Note: as we were only interested in finding the average, we had no reason to also save the grades somewhere

- Class Exercise 2:
    - Building on the previous exercises, consider that we also want to save the grades for each student and then display the grade and the average next to it. In this scenarion, we will make use of arrays
    - Solution: 
        ```c

        ```
