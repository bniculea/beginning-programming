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

12. Given a 2D Array with natural elements. Create a C++ program which will find the last digit of the product of the elements on the secondary diagonal with the property that they are minimal on their columns.

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
