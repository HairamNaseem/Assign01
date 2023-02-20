# Assign01
OS Theory Assignment 1, k213062

1: First we will download Kernel from kernel.org i did 4.19.272 Version [tarball] format. After it is downloaded extract the folder and in the extracted folder will make a new folder named 'hello'.

2: In that folder, Run a terminal, we'll make two files 'hello.c' (our task to run) and Makefile via terminal commands 'gedit hello.c' and gedit Makefile respectively

3: In hello.c write this code #include <linux/kernel.h> asmlinkage long sys_hello(void) { printk("Hello world\n"); return 0; }

4: In Makefile add this
obj-y := hello.o
![image](https://user-images.githubusercontent.com/123382738/220135523-0eff73a9-65b3-48ab-9385-ebc43475cd58.png)


5: We have to add the system call entry into the syscall_64.tbl file which keeps the name of all the system. For doing this we will open that file by running command in terminal which will open a file 

6: In the syscall_64.tbl file scroll down to line [334], in the next line put this line (which will be line 335), then save the file.

7: Now we have to add the prototype of our system call in the system’s header file. In kernel folder “/include/linux/syscalls.h” we have to add the prototype of our system call function in this file.

8: In this file we just have to add our function call in the system file by simply typing in the function name in the end, save it.

9: Open Makefile and in Extraversion put the value equal to the roll number

10: Press CTRL+F in the same file and search for "core-y", navigate to second instance and in the end of the line put " hello/"

11: We have to create a config file for our kernel. First, we search for the current config, copy the config, typing “cp /boot/config-4.10.0-28-generic /workingdirectory”

12: We will now write the configuration file

13: We have to clean our processes in the kernel by typing “make clean -j4” , we now type “make -j4” to start building our kernel
![image](https://user-images.githubusercontent.com/123382738/220135365-79654371-69f3-49c1-83a6-48d7077d19fd.png)

