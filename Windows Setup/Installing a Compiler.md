# Compiler Installation


## Available Options
A compiler is needed to translate your written C++ source codes into machine code that is readable by the CPU. These are the three most popular compilers to choose from:

<details>
<summary>1. Clang</summary>
Clang is the compiler front-end that handles C++ and integrates with LLVM backend infrastructure. It is known for short execution times and informative error messages,
</details>


<details>
<summary>2. GCC (GNU Compiler Collection)</summary>
Perhaps the most widely used compiler.
</details>


<details>
<summary>3. MSVC </summary>
Stands for Microsoft Visual C++, this easily integrates into Visual Studio and is actually part of the default installation of Visual Studio if C++ develop is selected prior to installation.
</details>


## Installing Clang and GCC with MYSYS2

1. Install [MYSYS2](https://www.msys2.org/). This is a software distribution and building platform on Windows. We need this to install MinGW, which is a compiler collection that allow you to install g++ (GNU) and clang++ (Clang).

2. Open MYSYS2, and run the following command:
```commandline
pacman -Syu
pacman S mingw-w64-x86_64-clang
pacman -S mingw-w64-x86_64-clang-tools-extra
```

3. Add the binary (bin) file to system variable path to ensure your system can find the compiler.
    - Navigate to MYSYS2. Click into 'mingw64' if you are using windows 64 bit. Click on the 'bin' file. Here you should find both compilers 'clang++.exe' and 'g++.exe'
    - Copy the directory of the bin file and add it as a system PATH. Under default conditions, this is: <u> C:\msys64\mingw64\bin </u>.

4. Verify that installation is correct by opening command prompt and running the command below. It should print the compiler version installed.
```
clang++ --version
```