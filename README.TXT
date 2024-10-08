CSCE 410/611/613: MP2 -- README.TXT

This file describes the content of this directory.
A file marked with (*) may be of some interest to the 
student, and he/she may want to have a look at it.
A file marked with (**) is important for this MP, and the
student is strongly encouraged to study the contents of this file.

Type qemu-system-x86_64 -kernel kernel.bin to run the kernel.

COMPILATION:
===========

FILE: 			DESCRIPTION:

makefile (**)		Makefile for MacOS or Linux 64-bit environment.
			Works with the provided linux image. 
		       	Type "make" to create the kernel.
linker.ld		The linker script.

OS COMPONENTS:
=============

FILE: 			DESCRIPTION:

start.asm (*)		The bootloader starts code in this file, which in turn
		  	jumps to the main entry in File "kernel.C".
kernel.C (**)		Main file, where the OS components are set up, and the
                    	system gets going.

assert.H/C		Implements the "assert()" utility.
utils.H/C		Various utilities (e.g. memcpy, strlen, etc..)

console.H/C		Routines to print to the screen.

machine.H/C (*)		Definitions of some system constants and low-level
			machine operations. 
			(Primarily memory sizes, register set, and
                        enable/disable interrupts, I/O ports)

machine_low.H/asm       Low-level machine operations (only status register
                        at this point)

simple_frame_pool.H/C (**) Definition and partial implementation of a
		      	 vanilla physical frame memory manager
		      	 that does NOT support contiguous
		      	 allocation. 
			 THESE FILES ARE NOT USED IN THE CODE
		      	 and are only present to provide an
		      	 example implementation of a bitmap with
		      	 associated bit-manipulation operations.

cont_frame_pool.H/C(**) Definition and empty implementation of a
			 physical frame memory manager that
			 DOES support contiguous
			 allocation. NOTE that the comments in
			 the implementation file give a recipe
			 for how to implement such a frame pool.
				 
