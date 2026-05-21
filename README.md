# Linux GNU Make homework

# Make_task_1

Part 1:
    1) Add several (at least 2) source code files (main.c, src1.c)
    2) Create 3 make files, each of which should create an executable file:
            2.1) The first makefile with one simple target that should assemble an executable file from all existing files in the directory
            2.2) The second make file must have several targets (one target for each source code file) without any auto-variables
            2.3) The third make-file is the same as the second, only with the use of auto-variables

Most important files: Makefile1 Makefile2 Makefile3 (Makefile for clean)
### To build respectively Makefile1, Makefile2, Makefile3

```bash
make -f Makefile1
make -f Makefile2
make -f Makefile3
```
### To clean 

```bash
make clean
``` 
# Make_task_2

  1) Create files with the source code:
            1.1) Three files (eg src1.c, src2.c, src3.c) with any (your choice) functions (1 function for each file)
            For each of the three files, a corresponding "*.mk" file must be added (for example, make1.mk, make2.mk, etc.) - their task is to create from the                 corresponding source code files - object files
            1.2) One file with main function (for example main.c)
                    Add the main Makefile which should:
                            1.2.1) Create an object file from a file with the main function
                            1.2.2) And also call the three *.mk files (added in point 1.1) using one of two methods
                                                Method 1: Using the command - "make -f"
                                                Method 2: Using the "include" command
                                    The choice of method depends on the value of the environment variable that needs to be added
                            1.2.3) Link all created object files into an executable file
                            1.2.4) Add target clean
            1.3) Add an empty file named "clean"

Most important files: Makefile
## To build ( needs enviroment variables )

```bash
BUILD_METHOD=include make 
BUILD_METHOD=make make 
```
## To clean 

```bash
make clean
```
Even if we have file named clean we added rule .Phony = clean so we ignore if file is up to date and execute anyway clean rules

If we enter the wrong BUILD_METHOD or ignore it: error: wrong BUILD_METHOD enviroment variable, allowed methods: make and include.


