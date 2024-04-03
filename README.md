# cmake

Create object file:

    g++ -c -Wall -Werror -fpic hello.cpp

Create shared library:

    g++ -shared -o libhello.so hello.o

Create static library:

    ar -rc libhello.a hello.o


Using .a file:
    
    g++ -L. -Wall -o main main.cpp -l:libhello.a


Using .so file:

    export LD_LIBRARY_PATH=$PWD:$LD_LIBRARY_PATH
    g++ -L. -Wall -Wl,-rpath=$PWD -o main main.cpp -lhello

or:

    g++ -L/home/username/folder -Wall -o test main.cpp -lhello
    
```/home/username/folder```: the path where the libhello.so is located:
