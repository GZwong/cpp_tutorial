# Setting up your IDE

## VS Code

1. Install C/C++ extension

    Without any extensions, VS Code is just a normal text editor. On the leftmost navigation bar of VS Code, go to Extensions, then find and install the C/C++ extension. This will allow VS Code to be linked to your installed compiler and provide **IntelliSense** (code autocompletion).

2. Run a simple Hello World program.

    - Create a new folder on where you want to keep a simple Hellow World program. It is recommended to make a 'Projects' Folder to store your future VS code projects. Under 'Projects', create a new folder called 'HelloWorld'. Open VS Code within this directory.
    - Create a 'helloworld.cpp' file (cpp extension indicates C++ files). Paste the following into the file:

        ```
        #include <iostream>
        int main()
        {
            std::cout << "Hello World, Welcome to VS Code" << std::endl;
        }
        ```
    - Under **Terminal** (on the top navigation bar), click on "Run Build Task". You will be prompted to select a build task. Here is where you select your compiler to compile the C++ code. Multiple options will show up if multiple compilers are installed. 
    
        *If no compilers are shown, it might be that the compiler is not added to the system PATH. Read 'Installing a Compiler' for additional information.*

    - Upon selecting the compiler and running the build task, you will find an executable 'helloworld.exe' appear in your directory. To run the file, go to terminal (in the same directory) and run:

        ```
        .\helloworld
        ```
        This should print "Hello World, welcome to VS Code" in your terminal.

3. *CONGRATULATIONS, YOU HAVE CREATED YOUR FIRST C++ PROGRAM!*


## Optional Configurations for C++
The section above shows the minimum requirements needed to run a C++ program in VS Code. However, there are still some highly recommended configurations:

### 

### CMake