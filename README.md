I followed the Makefile tutorial from http://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/

It is a very good tutorial that teaches you step by step the basics of the 'make' utility.
An interesting thing I learnt is that the 'make' utility is part of the GNU collection of tools for building operating systems. The GNU collection includes a Preprocessor, Compiler and Linker.

The General process of running a C file is:
1. Preproces: replace all DEFINE and #include references
2. Compile: transform the C code into Assembly, but leaving the references to files for for later (linking pahse; this allows not to compile all files everytime, and have some files possible stored in a company's library)
3. Link: link all .o files into a single output file that can be executed

When you write the command 'gcc' it means 'GNU C Compiler'. It has the following flags:
* -o ---> output into a file: ex:  gcc -o outputInThisFileName hello.c
* -c ---> only compile the files and create the object files, do NOT link them: ex: gcc -o outputCompiledFileHere -c hello.c
