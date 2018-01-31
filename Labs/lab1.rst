Lab 1: Booting a PC 
    $ uname -a # Show x86_64 or i386 

    Part1: PC Bootstrap
        1.1: Getting Started with x86 assembly 
            NSAM assembler: Intel syntax 
            GNU assembler: AT&T syntax 
            <<Brennan's Guide to Inline Assembly>>
                
        2.3: Simulating the x86 
            QEMU Emulator, a modern and relatively fast emulator. 
            > kerninfo # copy the contents of obj/kern/kernel.img onto the first few sectors of a real hard disk, insert that hard disk into a real PC, turn it on, and see exactly the same thing on the PC's real screen as you did above in the QEMU window.
            > The first PCs, which were based on the 16-bit Intel 8088 processor, were only capable of addressing 1MB of physical memory.
            > The Basic Input/Output System(BIOS), which occupies the 64KB region from 0x000F0000 through 0x000FFFFF.
            > BIOS is responsible for performing basic system initialization such as activating the video card and checking the amount of memory installed.After performing this initialization, the BIOS loads the operating system from some appropriate location such as floppy disk, hard disk, CD-ROM, or the network, and passes control of the machine to the operating system. 

The ROM BIOS:
    $ sudo apt install gdb 
        The target architecture is assumed to be i8086
        [f000:fff0]    0xffff0:	ljmp   $0xf000,$0xe05b
    From the top output you can conclude a few things:
        1. The IBM PC starts executing at physical address 0x000ffff0, which is at the very top of the 64KB area reserved for the ROM BIOS.
        2. The PC starts executing with CS = 0xf000 and IP = 0xfff0.
        3. The first instruction to be executed is a jmp instruction, which jumps to the segmented address CS = 0xf000 and IP = 0xe05b 
    
    BIOS in a PC is "hard-wired" to the physical address range 0x000f0000-0x000fffff.this design ensures that the BIOS always gets control of the machine first after power-up or any system restart.
    
    The real mode addressing: physical address = 16 * segment + offset. When the PC sets CS to 0xf000 and IP to 0xfff0,the physical address referenced

GDB:
    si(Step Instruction) command to trace into the ROM BIOS 
