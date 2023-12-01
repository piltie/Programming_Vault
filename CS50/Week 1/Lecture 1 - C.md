- Source code (código fonte): Computer only understands the information represented in binary, which is machine code.
- Source code (C) -> Compiler converts into -> Machine code (Ones and Zeros)
- Correctness, design and style
- CLI: Command Line Interface
	- clear - clean terminal
	- ./main - run code
	- code filename.c - create new file
- GUI: Graphical User Interface
- Semicolon after statement
- Library: code that someone else wrote (third party code), header file is what that declares it to exist
- Header files (stdio.h) contain info about the function in the standard I/O library
- Simplified documentation for C: manual.cs50.io
- (1.) CS50.h -> number of functions made by cs50 to make inputs and such easier for the class
	- https://cs50.readthedocs.io/libraries/cs50/
- Side effects are something more usual, different from return
- assignment (atribuição)
- IDE: CLion for C/C++
>	cmake_minimum_required(VERSION 3.26)
>	
>	project(CS50 C)
>	
>	set(CMAKE_C_STANDARD 11)
>	
>	add_library(CS50 cs50.c cs50.h)
>	
>	target_include_directories(CS50 PUBLIC .)

NOTES:

> **(1.) CS50 Library in windows**
> `cs50.h` is just a file. You can download it like you would any other file. If you place it in the MinGW include directory (check the MinGW documentation) and/or the search directory for your preferred editor, then you'll be able to `#include` it in your C files.
	The library itself is another story. The Makefile distributed with the source code is only configured for Mac and Linux, and won't work on Windows. You would have to [manually compile the source code into a library](https://www.codeproject.com/Articles/84461/MinGW-Static-and-Dynamic-Libraries) and place it in the MinGW library directory, then add it to your compile commands.
	- gcc -std=c11 -c cs50.c -o cs50.o
	- gcc -shared -o libcs50.so cs50.o
	- gcc -std=c11 -o main.exe main.c C:\Clibs\libcs50-11.0.2\src\libcs50.so
	- gcc -std=c11 -o main.exe main.c C:\Clibs\libcs50-11.0.2\src\libcs50.so -IC:\Clibs\libcs50-11.0.2\src