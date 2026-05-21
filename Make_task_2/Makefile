TARGET = program

#In the include variant the first rule file in Makefile becomes src1.o and the compilation stops, so we adding this rule to do all until target
all: $(TARGET)
#Enviroment variable with defining method of compilation
ifeq ($(BUILD_METHOD), include)

include make1.mk
include make2.mk
include make3.mk

$(TARGET): main.o src1.o src2.o src3.o
	gcc $^ -o $@

#make -f method
else ifeq ($(BUILD_METHOD), make)

$(TARGET): main.o src1.o src2.o src3.o
	make -f make1.mk
	make -f make2.mk
	make -f make3.mk
	gcc main.o src1.o src2.o src3.o -o $@
else
#if it its not clean command then its error
ifneq ($(MAKECMDGOALS),clean)
$(error error: wrong BUILD_METHOD enviroment variable, allowed methods: make and include)
endif
endif

main.o: main.c
	gcc -c main.c -o main.o

#Because in the task i was needed to create clean file the Makefile will see it was not changed
#so it will not execute the rules, so we add .PHONY rule to ignore the state of file clean and execute rules no matter what
.PHONY: clean

clean:
	rm -f *.o $(TARGET)