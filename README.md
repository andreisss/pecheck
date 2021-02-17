# pecheck

Why PE?
It represents a quite complete design for any exe file.

- Detaches code and data in sections, making it easy to manage the data separately from the program and link any string back to the assembly code.
- Each sections has separate memory permissions, which are basically a layer of security over virtual memory of each program running.
- file is expandable in memory
- support dynamic linking support relocation
- portable multiple processors

-- Exploring PE structure
Windows os, structure used by microsoft to rapresents an executable file or libs in win os.

--MZ header
