# Copyright (C) 2009 International Business Machines and others.
# All Rights Reserved.
# This file is distributed under the Eclipse Public License.

##########################################################################
#    You can modify this example makefile to fit for your own program.   #
#    Usually, you only need to change the five CHANGEME entries below.   #
##########################################################################

# CHANGEME: This should be the name of your executable
EXE = TutorialC

# CHANGEME: Here is the name of all object files corresponding to the source
#           code that you wrote in order to define the problem statement
OBJS = TutorialC.o

# CHANGEME: Additional libraries
ADDLIBS =

# CHANGEME: Additional flags for compilation (e.g., include flags)
ADDINCFLAGS =

##########################################################################
#  Usually, you don't have to change anything below.  Note that if you   #
#  change certain compiler options, you might have to recompile Ipopt.   #
##########################################################################

# C Compiler command
CC = gcc

# C Compiler options
CFLAGS = -O2 -DNDEBUG 

# additional C Compiler options for linking
CLINKFLAGS = 

prefix=/usr/local
exec_prefix=${prefix}

# Include directories
INCL = `PKG_CONFIG_PATH=/usr/local/lib/pkgconfig: pkg-config --cflags ipopt` $(ADDINCFLAGS)
#INCL = -I${prefix}/include/coin  -DIPOPTLIB_BUILD $(ADDINCFLAGS)

# Linker flags
LIBS = `PKG_CONFIG_PATH=/usr/local/lib/pkgconfig: pkg-config --libs ipopt` -lc++
#LIBS = -L${exec_prefix}/lib -lipopt -framework Accelerate  -ldl -lc++

all: $(EXE)

.SUFFIXES: .c .o

$(EXE): $(OBJS)
	$(CC) $(CLINKFLAGS) $(CFLAGS) -o $@ $(OBJS) $(ADDLIBS) $(LIBS)

clean:
	rm -rf $(EXE) $(OBJS) ipopt.out

.c.o:
	$(CC) $(CFLAGS) $(INCL) -c -o $@ $<
