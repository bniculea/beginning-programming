# Multidimensional arrays exercises - Taken from pbinfo.ro

## Clasa IX-a => Tablouri Bidimensionale(matrice) => Parcurgerea matricelor patratice => Usoare

1. Let's consider a square matrix with N rows and N columns. In this matrix we have 4 areas:
    - `1`, the zone which contains the elements which are strictly above the main diagonale and strictly above the second diagonale
    - `2`, the zone which contains the elements strictly above the main diagonale and strictly below the second diagonale.
    - `3`, the zone which contains the elements strictly below the main diagonale and strictly below the second diagonale.
    - `4`, the zone which contains the elements strictly below the main diagonale and strictly above the second diagonale.
- Given a squared matrix and an integer number `Z`, which representsan area from the matrix, create a program which computes the sum of the elements in the Z area.
    - Solution:
        ```C++
            #include <iostream>
            using namespace std;

            int main()
            {
                int mat[4][4]={
                        {1,2,3,4},
                        {5,6,7,8},
                        {9,10,11,12},
                        {13,14,15,16}
                };

                int z;
                int sum =0;
                cout<<"Enter the zone for which you want to compute the sum of the elements: (1-4) ";
                cin >> z;
                for(int i = 0; i < 4; i++){
                    for(int j = 0; j < 4; j++) {
                        if(z == 1 && (j > i && j < 4-i-1)) {
                            sum+= mat[i][j];
                        } else if (z == 2 &&  ( j > i && j > (4 -i-1) )) {
                            sum+= mat[i][j];
                        } else if (z == 3 && (i > j && j > (4-i-1))) {
                            sum+= mat[i][j];
                        } else if (z == 4 && (i > j &&  j < (4-i-1) )) {
                            sum+= mat[i][j];
                        }
                    }
                }
                cout<< "The sum of the elements in the zone #"<<z<< " is: " << sum;
                return 0;
            }

        ```
2. In the 9th grade class there are `M` students, numbered from `1` to `M` and each of them has a preferred number `P`. Bored by the Informatics class, they have invented the following game:
    - On a math paper, they draw a board of dimension `N`, which is formed from `N` rows and `N` columns, numbered from `1` to `N`. Each line and row has `N` squares