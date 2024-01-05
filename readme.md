> [!Warning]  
> This project is at a very early stage of development. Do not use! Highly unstable!


# IRA format

### What is it for?
IRA is a binary format for storing images as bytecode of compact virtual machine.
When you open a file in this format the virtual machine executes the code
inside the file and visualizes the result of the execution.
This format is theoretically more optimal than any other in terms of file size,
provided there is a smart enough converter into this format.
However, such a converter has not been implemented yet.
Also, the format itself is at a very early stage of development.


### Ira file structure
 *  Header: 8 bytes
 *   *  4 bytes = `00 69 72 61` = `".ira"`
 *   *  1 byte  = version number
 *   *  1 byte  = a bunch of flags:
 *   *   *  Does the file have function names embedded?
 *   *   *  Does it have argument ranges for the functions?
 *   *   *  Embedded file description?
 *   *   *  Source code?
 *   *  4.09 bits = desired size of available memory : 0..16
 *   *  3.91 bits = flags to enable builtin functions : 1..15
 *   *   *  basic control flow operations?
 *   *   *  i32 operations?
 *   *   *  f64 operations?
 *   *   *  ?????????
 *   *  1 byte = number of one-byte opcodes : uint8
 *  Optional description.
 *  Optional source code.
 *  Bytecode itself:
     *  Private functions.
     *  Public functions in this format:
         *  Optional function name.
         *  Optional argument type and range.
         *  Id of private function to call.
 *  Content of first bytes of linear memory.

Problems:
 *  Redundant byte value 0 inside linear memory content.


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
