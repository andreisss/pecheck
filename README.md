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
 
 + ## Optional header
 
 ![alt text](  https://i.ibb.co/BLZYTr4/report.jpg)
 
 ![alt text]( https://i.ibb.co/6HtS0cp/5657.jpg)

 
  - Magic identifies the type of system or PE file (it's x86 or x64)
 -  AddressOfEntryPoint very important field - point to the starting point of the program execution. 
 -  ImageBase this is the address where the program was designed to be load in the virtual memory. If the program has a relocation section, it can be moved somewhere else, if it will overlap with another executable loaded in the same address. 
 -  SectionAlignment the size og each section should be aligned to this value while loaded in the memory (generally is 0x1000) 
 - FileAlignment the size of each sections in the PE file (as well the size of headers) has to be aligned to this number. For example if the section the size is 0x1164 and the file alignement is 0x200 the section will be changed to 0x1200 on the hard disk.

 + ## Data Directory
 
 ![alt text]( https://i.ibb.co/7SN6B4v/data-dir.jpg)

 - Import table  This rapresents the code functions or api that the program doesn't include but want to import from others executable files or libs or DLLs.
 - Export table  This rapresents the code functions or api that the program includes in its code,as others app can use it rather than writes from scratch.
 - Resource table The packages files with the program such as icons, imgs and more. Sometimes malware hide dll or exe to load in memory. 
 - Relocation table It's used to fix addresses in the code when the PE file is loaded to another place in memory.
 - TLS table could be used to bypass debugger. 

+ ## Section Table
 - Name the name os the section
 - VirtualAddress Pointer to the beginning of the section in memory, relatively to the start of the file. Used to be called RVA addresses.
 - VirtualSize the size of the section in memory
 - SizeOfRawData the size of section on HD
 - PointerToRawData the point of section in the file on HD
 - Characteristics mwmory protections flags
