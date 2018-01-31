Tools Used in 6.828
	
	Host System:
		Ubuntu Server 16.0.3 LTS
	Virtualbox (Mac OS X host/ Ubuntu server 16.0.3)
        Internet connection:
            Setting: 
                Chose "Bridged Adapter" and "PCnet-FAST III" in Network Settings. 
        SSH and Virtualbox:
            端口转发：
                使用端口转发链接到虚拟机，可以避免在虚拟机上配置格外的网卡，且不受主机局域网的影响。
                网络->NAT(网络地址转换)->P(端口转发)
                    名称：SSH
                    协议：TCP
                    主机IP：
                    主机端口：8022
                    子系统IP：
                    子系统端口：22 
                配置好本机端口号和虚拟机SSH端口号（默认22）
                $ ssh -p 8022 username@127.0.0.1 


	Tools Used:
		QEMU: x86 emulator, for running xv6 kernel 
		Compiler Toolchain: assembler,linker, C compiler, debugger 

GNU Toolchains and Qemu Install:
	
    $ sudo apt-get update 
	$ sudo apt-get install build-essential
		build-essential: is a package for developers. it contains most of the tools you will need during your code work,like gcc, gdb, objdump
	$ sudo apt-get install libc-dev:i386 

    $ sudo apt-get install gcc-multilib
		This lib is required for the multi-thread support 
	$ sudo apt-get install qemu 
        qemu is a computer simulator 
    $ sudo apt-get install git-core 

Test Environment 
    $ objdump -i 
        objdump - display information from object files [should say "elf32-i386"]
    $ gcc -m32 -print-libgcc-file-name 
     

xv6 Source Code:
    $ mkdir ~/.6.828
    $ cd 6.828
    $ git clone git://pdos.csail.mit.edu/xv6/xv6.git 
        will download the xv6 source code for you.
    $ cd ~/.6.828/xv6 
    $ chmod 700 -R xv6 
    $ make 
    $ make qemu -nographic 
        Try qemu -nographic to bypass the SDL 

