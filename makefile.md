##### This file must not have the .md extension when used.
The syntaxis of the make file it's easy. Just input:
		make (whatever)
and it should compile and then run. The code for it is the following:

		.SUFFIXES:
		.PHONY:		//here the part after the command "make" (example: prog)

		compilador 	:= //whatever you need to use (gcc, g++, mpicxx)
		flagsc 		:= //any additional option without arguments (-g -Wall)

		//prog: //name of the file to be compiled
			//command to run the file (e.g: mpirun -np x name_file)

		%: %.cpp
			$(compilador) $(flagsc) -o $@ $<

		clean:
			rm -f (file_name)
