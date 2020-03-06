# Makefile with Boost Test Library

```Makefile
# Compiler
CC = g++
# compiler flags
CFLAGS = -g -c -Wall
# using libraries
LDFLAGS = -DBOOST_TEST_DYN_LINK -lboost_unit_test_framework
# path for headers
INCPATH = -IC:/dev/mingw/include
# path for libraries
LIBSPATH = -LC:/dev/mingw/lib
# compile object files
OBJECTS  = test.o foo.o


.PHONY: all clean install uninstall
# default target
all: pattern

pattern: $(OBJECTS)
    $(CC)  $(LIBSPATH) $(LDFLAGS) $(OBJECTS) -o pattern
%.o: %.cpp  
    $(CC) $(CFLAGS) $(INCPATH) $<
# test.o: test.cpp foo.h
#    $(CC) $(CFLAGS) $(INCPATH) test.cpp 
# foo.o: foo.cpp foo.h
#    $(CC) $(CFLAGS) $(INCPATH) foo.cpp 

clean:
    rm -rf *.o pattern
```
