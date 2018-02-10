# xv6Kernel
参照MIT6.828 Operating System 相关课程学习xv6源代码

## Reading book-rev10.pdf 
	*名词解释*
	kernel: a specal program that privides services to running prigrams.
	process: has memory containing **instructions**,**data**,**stack**
	shell: is an ordinary program that reads commands from the user and executes them. 

	The kernel uses the CPU's hardware protection mechanisms to ensure that each process executing in user space can access only its own memory. 

	**系统调用**
	fork: A process may create a new process using the fork system call. 
		-- child process with exactly the same memory contents as the parent process 
		-- fork returns in both the parent and child, In the parent, fork return the child pid, in the child, it return zero. 
