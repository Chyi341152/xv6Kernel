6.828 lab tools guide 
    
    Overview of the JOS environment and useful GDB and QEMU commands 

    # Debugging tips:
        $ qemu-gdb (or qemu-gdb-nox)  # make QEMU wait for GDB to attach 
        $ qemu -d # generate detail log of interrupt 
        $ info mem # debug virtual memory issue 
        $ info pg # lots of detail, display the current page table 
        $ info threads # debug multiple CPUs thread-related commands 

    # 
