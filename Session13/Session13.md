# Multidimensional arrays exercises - Taken from pbinfo.ro

## Clasa IX-a => Tablouri Bidimensionale(matrice) => Parcurgerea matricelor patratice => Mediu

11. Create a C++ program which will scroll through a matrix in spiral, clockwise. The matrix has `n` rows and `n` columns

    - Sample Input:
      - n = 4
      - ```json
          1   2   3   4
          5   6   7   8
          9   10  11  12
          13  14  15  16
        ```
    - Sample Output:
      ```json
          1 2 3 4 8 12 16 15 14 13 9 5 6 7 11 10
      ```
    - Solution:

      ```c++
        #include <iostream>
        #include <fstream>

        using namespace std;

        int main() {
            ifstream fin;
            ofstream fout;
            fin.open("spirala.in");
            fout.open("spirala.out");

            int n;
            fin >> n;
            int mat[n][n];
            for (int i = 0; i < n; i++) {
                for (int j = 0; j < n; j++) {
                    fin >> mat[i][j];
                }
            }

            int rowStartIndex = 0;
            int rowEndIndex = n - 1;
            int columnStartIndex = 1;
            int columnEndIndex = n - 1;

            while (rowStartIndex < rowEndIndex) {
                //displayTop;
                for (int i = rowStartIndex; i <= rowEndIndex; i++) {
                    fout << mat[rowStartIndex][i] << " ";
                }

                // display last column
                for (int i = columnStartIndex; i <= columnEndIndex; i++) {
                    fout << mat[i][columnEndIndex] << " ";
                }
                columnStartIndex++;
                columnEndIndex--;

                //display bottom row
                for (int i = columnEndIndex; i >= rowStartIndex; i--) {
                    fout << mat[rowEndIndex][i] << " ";
                }

                // display first column
                for (int i = columnEndIndex; i > rowStartIndex; i--) {
                    fout << mat[i][0] << " ";
                }

                rowStartIndex++;
                rowEndIndex--;

            }
            return 0;
        }

      ```

12. Given a 2D Array with natural elements, create a C++ program which will find the last digit of the product of the elements on the secondary diagonal with the property that they are minimal on their columns.

- Sample Input:
  ```json
    4
    3 4 90 10
    25 2 7 9
    18 3 10 4
    3 7 20 3
  ```
- Sample Output: `1`
- Solution:

  ```c++
    #include <iostream>
    #include <fstream>

    using namespace std;

    int main() {
        ifstream fin;
        ofstream fout;
        fin.open("mincols1.in");
        fout.open("mincols1.out");
        int n;
        fin >> n;
        int columnsMin[n];

        int mat[n][n];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                fin >> mat[i][j];
            }
        }

        for(int i = 0; i < n;i++) {
            columnsMin[i] = mat[i][0];
            for(int j = 0; j < n; j++) {
                if(mat[j][i] < columnsMin[i]){
                    columnsMin[i] = mat[j][i];
                }
            }
        }

        int product = 1;

        for(int i =0; i < n; i++){
            for(int j = 0; j < n; j++) {
                if((j == n-i-1) && (mat[i][j] ==  columnsMin[j])) {
                    product *= mat[i][j];
                }
            }
        }

        fout << product % 10;
        return 0;
    }

  ```

13. Given a 2D array with integer elements, create a C++ program which will compute the average of the strictly positive elements in the matrix which are located below the main diagonal.

- Sample Input (`medpoz.in`):
  ```json
    4
    -1 2 4 5
    0 6 3 1
    2 4 2 0
    3 -5 1 -3
  ```
- Sample Output: `2.5`
- Solution:

  ```c++
    #include <iostream>
    #include <fstream>

    using namespace std;

    int main() {
        ifstream fin;
        ofstream fout;
        fin.open("medpoz.in");
        fout.open("medpoz.out");
        int n;
        fin >> n;

        int mat[n][n];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                fin >> mat[i][j];
            }
        }

        double sum = 0.0;
        int count = 0;

        for(int i = 0; i < n; i++) {
            for(int j =0; j < n; j++) {
                if(i > j && mat[i][j] > 0) {
                    sum+= mat[i][j];
                    count++;
                }
            }
        }

        fout << sum / count;

        return 0;
    }

  ```

14. After the disaster caused by the hacker Gigel (#Overload), the network administrator decided to take action.

It is responsible for a network with n \* n computers arranged in the form of a 2D array with n rows and n columns, in which each computer is connected to adjacent computers (up, right, left, down), each computer in row n is connected to the computer on row 1 and the same column, and each computer on row n is connected to the one on column 1 and the same row.

In this network, there are encrypted computers that cannot receive corrupt data packets. Unencrypted computers can receive corrupt packets but cannot process them. Their behavior is different: when an unencrypted computer receives a packet of data, it forwards it to the next computer in the same direction until they encounter an encrypted computer. The computer that contains the corrupted data packet can then receive a command to forward it in another direction.

The network becomes overloaded if the corrupted packet reaches a row or column that contains only unencrypted computers, so that it can be transmitted indefinitely.

Hacker Gigel took advantage of this network weakness and managed to give commands through computer terminals so that the data packet was transmitted indefinitely between them, overloading the network, (see the issue #Overload).

The network administrator has decided to encrypt enough computers to avoid any possibility of network overload. Because encrypting a single computer takes a long time, the administrator wants to know the minimum number of computers that need to be encrypted so that the Gigel hacker can no longer have fun with the network.

The `encryption.in` input file contains the number n on the first line, followed by n rows with n numbers. A value of 1 represents an already encrypted computer, and a value of 0 represents an unencrypted computer.

The `encryption.out` output file will contain the Sol number on the first line, representing the minimum number of computers that need to be encrypted, and on the next Sol rows a pair of x and y numbers representing that on the x line and y column the computer must be encrypted.

- Sample Input (`criptare.in`):

  ```json
  5
  0 0 0 0 0
  1 1 1 1 1
  1 0 1 1 0
  0 1 0 1 0
  0 0 0 0 0
  ```

- Sample Output (`criptare.out`):
  ```json
    2
    1 1
    5 3
  ```
- Solution:

  ```c++

  ```
