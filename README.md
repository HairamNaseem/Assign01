# Assign01
OS Theory Assignment 1, k213062

1: First we will download Kernel from kernel.org i did 4.19.272 Version [tarball] format. After it is downloaded extract the folder and in the extracted folder will make a new folder named 'hello'.
![image](https://user-images.githubusercontent.com/123382738/220141070-0a1f0243-9e17-4d32-b7c4-45c717924d05.png)


2: In that folder, Run a terminal, we'll make two files 'hello.c' (our task to run) and Makefile via terminal commands 'gedit hello.c' and gedit Makefile respectively

3: In hello.c write this code #include <linux/kernel.h> asmlinkage long sys_hello(void) { printk("Hello world\n"); return 0; }

4: In Makefile add this
obj-y := hello.o
![image](https://user-images.githubusercontent.com/123382738/220135523-0eff73a9-65b3-48ab-9385-ebc43475cd58.png)


5: We have to add the system call entry into the syscall_64.tbl file which keeps the name of all the system. For doing this we will open that file by running command in terminal which will open a file 

6: In the syscall_64.tbl file scroll down to line [334], in the next line put this line (which will be line 335), then save the file.
![image](https://user-images.githubusercontent.com/123382738/220136217-201ef25b-3c54-49e7-973f-f042fffa18d3.png)


7: Now we have to add the prototype of our system call in the system’s header file. In kernel folder “/include/linux/syscalls.h” we have to add the prototype of our system call function in this file.

8: In this file we just have to add our function call in the system file by simply typing in the function name in the end, save it.
![image](https://user-images.githubusercontent.com/123382738/220136355-a73ee28f-8b19-40ee-b4c8-297390c759ab.png)


9: Open Makefile and in Extraversion put the value equal to the roll number

10: Press CTRL+F in the same file and search for "core-y", navigate to second instance and in the end of the line put " hello/"
![image](https://user-images.githubusercontent.com/123382738/220136523-bf851848-4c17-44e3-92bb-f814016e9722.png)


11: We have to create a config file for our kernel. First, we search for the current config, copy the config, typing “cp /boot/config-4.10.0-28-generic /workingdirectory”

12: We will now write the configuration file

13: We have to clean our processes in the kernel by typing “make clean -j1” , we now type “make -j1” to start building our kernel and then install modules through command "make modules_install install".

![image](https://user-images.githubusercontent.com/123382738/220135365-79654371-69f3-49c1-83a6-48d7077d19fd.png)

![image](https://user-images.githubusercontent.com/123382738/220696607-716dafad-5b89-47e2-9492-ad56ed2be404.png)

14: now we will restart ubuntu and then choose ubuntu version with our roll number
![image](https://user-images.githubusercontent.com/123382738/221155606-7db1cbda-f48d-485b-9986-f4d24dc46e0d.png)

15: write "uname -r" in ubuntu to check if you have done correctly
![image](https://user-images.githubusercontent.com/123382738/221157023-643e5716-f1d2-43a7-b267-6c1efb146da9.png)

16: now make a c file and write the following code to check if the system call you made works
![image](https://user-images.githubusercontent.com/123382738/221158495-f523860e-541e-4734-8738-01365854781d.png)

17: you can verify through writing "dmesg" in terminal
![image](https://user-images.githubusercontent.com/123382738/221158909-c262bff3-45bd-421b-b3df-7a02b60cedb0.png)




