This project is at a very early stage of development. Do not use! Highly unstable!


# IRA format

### What is it for?
IRA is a binary format for storing images as bytecode of compact virtual machine.
When you open a file in this format the virtual machine executes the code
inside the file and visualizes the result of the execution.
This format is theoretically more optimal than any other in terms of file size,
provided there is a smart enough converter into this format.
However, such a converter has not been implemented yet.
Also, the format itself is at a very early stage of development.


### Structure
Header: 8 bytes
	4 bytes = 00 69 72 61 = ".ira"
	1 byte  = version number
	1 byte  = a bunch of flags:
		Does the file have function names embeded?
		Does it have argument ranges for the functions?
		<!-- Repeat linear memory content? -->
		Embeded file description?
		Source code?
	4.09 bits = number of halfbyte opcodes : 0..16
	3.91 bits = flags to enable builtin functions : 1..15
		basic control flow operations?
		i32 operations?
		f64 operations?
		?????????
	1 byte = number of one-byte opcodes : uint8
Names of public functions or number of public functions depending on the corresponding flag.
Optional types or ranges of arguments of public functions.
Optional description.
Optional source code.
Bytecode itself: just a list of functions.
Content of first bytes of linear memory.

Problems:
* Where to store linear memory size?
* Redundant byte value 0 inside linear memory content.


### Progress
- [ ] Try not to waste time on this project and do something useful instead.
- [x] Come up with a project name and file extension.
- [ ] Design virtual machine instruction set.
- [ ] Design file format structure.
- [ ] Implement encoder.
- [ ] Implement decoder.
