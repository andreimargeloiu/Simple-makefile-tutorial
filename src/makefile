# v1
# hellomake: hellomake.c hellofunc.c
    # gcc -o hellomake hellomake.c hellofunc.c -I .

# if you want to run your program, you need to do:
# (this workd on Linux/MacOS)
# 	chmod +x hellomake
#	./hellomake
# ... you should see the output of the program


# v2 - it uses the .o files from the previous phase
# CC=gcc
# CFLAGS=-I.
# hellomake: hellomake.o hellofunc.o
#     $(CC) -o hellomake hellomake.o hellofunc.o


# v3 - make the compilation and linking phases different
#CC=gcc
#CFLAGS=-I. # this tells to gcc to look into the folder for the corresponding .h files
#DEPS = hellomake.h

# compialtion phase
# $@ is the name of the make shortcut ex: 'hellofunc.o' in the case below
# $< is the name of the first element in the dependency list ex: 'hellofunc.c'
# this tells to make that the file ending in '.o' depends on the equivalent filename ending in '.c' and the DEPS list

#%.o: %.c $(DEPS)
#	$(CC) -o $@ -c $< $(CFLAGS)
#	echo "I am build the file $($@)"

#hellomake: hellomake.o hellofunc.o
#	$(CC) -o hellomake hellomake.o hellofunc.o


# v4 - make sthe hellomake more general
#CC=gcc
#CFLAGS=-I.
#DEPS = hellomake.h
#OBJ = hellomake.o hellofunc.o

# compilation
# %.o: %.c $(DEPS)
	# $(CC) -o $@ -c $< $(CFLAGS)

# linking
#hellomake: $(OBJ)
#	$(CC) -o $@ $^ $(CFLAGS)

#clear:
#	rm hellomake $(OBJ)


# v5 - separate the file (.c, .o, .h) into different subfolders (src, obj, include, library)
# run this script from inside the ./src folder
IDIR =../include
CC=gcc
CFLAGS=-I$(IDIR)

ODIR=obj
LDIR =../lib

LIBS=-lm

_DEPS = hellomake.h
DEPS=$(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = hellomake.o hellofunc.o
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))

# compile
$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -o $@ -c $< $(CFLAGS)

# link
hellomake: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~
