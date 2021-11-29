## Software tools for C Programming
WINDOWS OS
LINUX OS

## Software Setup on Windows OS for C Programming
IDE
Visula Studio Code for compiling and debuggin the code.

Build tools
Make Installer from GNUWin32 for automating the build without usign IDE
Code Analysis
cppcheck for Static Analysis
Dr. Memory for Heap analysis
Memory Sanitization using gcc and -fsanitize option
Source code Management
git
Test Framework
Unit test
Documentation
Doxygen

## Software Setup on Linux OS for C Programming
IDE
Visula Studio Code for compiling and debuggin the code.
Compiling and running without IDE
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install build-essential
Compiling and running
    gcc filename.c -o outputname.out
    ./outputname.out
Build tools
Make for automating the build
    sudo apt-get install cmake
Code Analysis
cppcheck for Static Analysis
Valgrind for Heap analysis. Check usage here
    sudo apt-get install valgrind
Memory Sanitization using gcc and -fsanitize option
Source code Management
git
Test Framework
Unit test
Documentation
Doxygen
