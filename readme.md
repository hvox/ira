> [!Warning]
> This project is at a very early stage of development. Do not use! Highly unstable!


# IRA format

### What is it for?
IRA is a binary file format for storing images as bytecode of a compact virtual machine.
When you open a file in this format the virtual machine executes the code
inside the file and visualizes the result of the execution.
This format is theoretically more optimal than any other in terms of file size,
provided there is a smart enough converter into this format.
However, such a converter has not been implemented yet.
Also, the format itself is at a very early stage of development.


### Ira file structure
 *  Header: 8 bytes
     *  4 bytes = `00 69 72 61` = `.ira`
     *  1 byte = version number = 0 (pre-release)
     *  1 byte = number of one-byte opcodes : 0..255
     *  2 bytes = size of linear memory in 64KiB-pages : 1..65536
 *  Bytecode of functions.
    The last defined function is called and it is expected that this
    function will generate the image and place it in the linear memory.
    Image should be generated directly after bytes defined below.
 *  First bytes of program's linear memory.

Problems:
 *  I don't have enough free time to do even a little bit of work on the project.


### Progress
- [ ] Try not to waste time on this project and do something useful instead.
- [x] Come up with a project name and file extension.
- [ ] Design virtual machine instruction set.
- [ ] Design file format structure.
- [ ] Implement experimental mini-encoder.
- [ ] Implement experimental mini-decoder.
- [ ] Gather statistics.
- [ ] Decide the fate of halfbytes.
- [ ] Stabilize design.
- [ ] Implement encoder.
- [ ] Implement decoder.
