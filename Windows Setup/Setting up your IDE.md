# Setting up VS Code for C++

## Getting VS Code to work
This section highlights the bare minimum to configure VS code to run any C++ code.

1. Install C/C++ extension

    Without any extensions, VS Code is just a normal text editor. On the leftmost navigation bar of VS Code, go to Extensions, then find and install the C/C++ extension. This will allow VS Code to be linked to your installed compiler and provide **IntelliSense** (code autocompletion).

2. Write a Hello World Program (.cpp file).

    - Create a new folder on where you want to keep a simple Hellow World program. It is recommended to make a 'Projects' Folder to store your future VS code projects. Under 'Projects', create a new folder called 'HelloWorld'. Open VS Code within this directory.
    - Create a 'helloworld.cpp' file (cpp extension indicates C++ files). Paste the following into the file:

        ```
        #include <iostream>
        int main()
        {
            std::cout << "Hello World, Welcome to VS Code" << std::endl;
        }
        ```
3. Build the Hello World program as an executable (.exe).
    - Under the global **Terminal**, click on "Run Build Task". You will be prompted to select a build task. Here is where you select your compiler to compile the C++ code. Multiple options will show up if multiple compilers are installed. 
    
        *If no compilers are shown, it might be that the compiler is not added to the system PATH. Read 'Installing a Compiler' for additional information.*

    - Upon selecting the compiler and running the build task (g++ is recommended), you will find an executable <u>helloworld.exe</u> appear in your directory. To run the file, go to **terminal** (either within VS code or windows), and run either one of:

        ```
        helloworld.exe     # for cmd
        .\helloworld       # for powershell
        ```
        This should print "Hello World, welcome to VS Code" in your terminal.

**CONGRATULATIONS, YOU HAVE CREATED YOUR FIRST C++ PROGRAM!**

## (Optional but Recommended) Configurations for C++
The section above shows the minimum requirements needed to run a C++ program in VS Code. However, there are still some highly recommended configurations:

### Debugger (HIGHLY RECOMMENDED)
At this stage, you can build C++ source codes into an executable and you can run it. If there are errors, a debugger will be invaluable in troubleshooting! With a debugger, you can add 'breakpoints' within your code. When debugging, your code will stop at the designated breakpoints, allowing you to view the variables etc.

These are the steps to intall a GDB (GNU Debugger):

1. Open MYSYS2 (the same terminal where you installed the compiler).
2. Run the following command to install the gdb:

    ```
    pacman -S mingw-w64-x86_64-gdb
    ```
3. Under your <u>mysys2/mingw64/bin</u> folder, you should see the debugger <u>gdb.exe</u>. Add this directory to PATH if you have not already (you should have added this to PATH already when installing your compiler!).

4. Go to your <u>helloworld.cpp</u> file and click **Run & Debug** on the left pane. A prompt will appear for you to select your debug configuration. I selected the option with 'g++.exe' though others should work as well.

5. This will create a <u>launch.json</u> file which stores your debugging configuration - you do not have to choose the debugger everytime you click on **Run & Debug**!

### CMake

## (Optional) Understanding VS Code
VS Code is probably the most difficult IDE to setup due to its customizability. It can be the most powerful if you know what you are doing!

- VS Code Tasks Options (<u>task.json</u>)

    - Previously, to build the program, you either went to **terminal -> Run Build Task** or pressed **Ctrl+Shift+B**. Now, go to **Terminal -> Configure Tasks**. This will open a <u>tasks.json</u> file under your <u>.vscode</u> folder. This <u>.json</u> file defines what happens when you click on **Terminal -> Run Task**. This task can simply be to build the application (Run Build Task). Users can also change the <u>task.json</u> file so that **Run Task** not only build the application, but also run the executable subsequently, by changing the "command field" within the <u>task.json</u> file.
    - The <u>task.json</u> essentially stores this configuration of the user's tasks, so that it will remember how you want to run your task when you click on **Run Task**.

###
- VS Code Launch Options (<u>launch.json</u>)

    - Upon setting up your debugger like shown above, you will notice a <u>launch.json</u> file under the <u>/.vscode</u> folder.
    
    - While <u>task.json</u> stores the user's choice on what task(s) to run, the <u>launch.json</u> file saves the users' debugging configuration, so that you do not have to specify the compiler, debugger etc. everytime you debug the application.
    
    - You can also play around with the arguments within the <u>launch.json</u> file to improve debugging experience. For example, there are arguments which may increase the level of detail of the error message returned by the debugger, though these are out of the scope of this tutorial.