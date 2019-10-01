# Steps to run a C++ command from Command Line
1. Download a C++ compiler from here https://sourceforge.net/projects/mingw/
2. Install the compiler
   - Select the gcc++ compiler from the list
   - Add the folder where you have installed the IDE to the Windows Path
3. Create a new C++ program using your IDE at choice
4. Navigate to the location of the `.cpp` file and open a terminal in the same location
4. Compile your code using:
    - `g++ -o <your_program_name> <your_cpp_file>` e.g `g++ -o main main.cpp`
5. Run your program
    - If your program name was `main` then type `main.exe` and press enter

### Run the program below which displays all the arguments passed to a c++ application run from CLI
```c
#include <iostream>

using namespace std;

int main(int argc, char** argv)
{
    cout<<"You have entered " << argc << " arguments" << endl;
    cout<< "Arguments are: " << endl;
    for(int i = 0; i < argc; i++){
        cout << "#" << i << ": " << argv[i] << endl;
    }
    return 0;
}

```