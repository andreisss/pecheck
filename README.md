# EXPLORING PE STRUCTURE 

Why PE?
It represents a quite complete design for any exe file.

- Detaches code and data in sections, making it easy to manage the data separately from the program and link any string back to the assembly code.
- Each sections has separate memory permissions, which are basically a layer of security over virtual memory of each program running.
- file is expandable in memory
- support dynamic linking support relocation
- portable multiple processors


# why PE

Windows os, structure used by microsoft to rapresents an executable file or libs in win os.

+ ## MZ header

![alt text](https://qhf0l1i8l8u25b2354fr8h39-wpengine.netdna-ssl.com/wp-content/uploads/2019/04/Picture1-480x165.jpg)

 The dos header starts with MZ and end with e_lfanew which points to the start of portable executable header. or PE header.


+ ## PE Header starts with 2 letters

![alt text](https://bufferoverflows.net/wp-content/uploads/2019/08/Selection_168-1024x397.jpg)


+ ## File header

 ![alt text](https://i.ibb.co/sbvrsDp/123.jpg)

 - Machine rapresents the processor type ex. 0x14c is Intel 386 or later.
 - Numberofsections the number of sections that follow the header
 - TimeDateStamp the exact time and date where the tool was compiled
 - Characteristics rapresents the exact type of file, program or dll or maybe sys driver.
 

 
 
