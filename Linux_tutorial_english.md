# Basic Linux Practice
## Installing Ubuntu on Windows
Most members of the Marine Biogenomics lab use Windows as their operating system, so we need to use the Linux subsystem with a Linux distribution (GNU/Linux), commonly known as a "distro". Mac users do not need a distro as their terminal already has native GNU/Linux. To install Ubuntu as a distro on Windows, we need to go to the Microsoft Store, type "Ubuntu" in the search bar, select and install the first option as shown in the figure.

<p align="center">
    <img src="https://github.com/user-attachments/assets/d0a2795d-4718-4c68-ad5f-8cb416849882" width="500">
</p>

# Common Problems
If you get the following error when opening the application:
```bash
Installing, this may take a few minutes...
WslRegisterDistribution failed with error: 0x8007019e
Error: 0x8007019e The Windows Subsystem for Linux has not been enabled.

Press any key to continue...
```

You need to go to the Windows search bar, type Windows Powershell to enter the Windows shell, then type the following command:


```bash
wsl --install
```
This will install the subsystem for Windows. Once the installation is complete, you should restart your personal machine. Then open Windows Powershell again and type:

```bash
wsl
```
It will download the updates and once they are finished, you can open the Ubuntu application. You should see your Linux shell like in the following image:

<p align="center"> <img src="https://github.com/user-attachments/assets/bff1f5d8-4916-4d23-ab3d-2f878b58a1f1" width="500"> </p>

## About Linux

Why do we use Linux in bioinformatics? First, most bioinformatics tools were designed and optimized in Linux, examples include BWA, Bowtie, among other tools. Second, Linux is secure due to the permissions and access controls configured within the system. Third, it is stable so there is no need to update the operating system periodically as in Windows. Finally, it is open-source which reduces costs since you don't have to pay for programs, increases collaboration opportunities and makes each tool transparent as we can see the source code.
In Linux, we will be working with the command line because there are no graphical interfaces for many of the tools used in bioinformatics. A command line allows us to give specific instructions to perform tasks. This is important because it gives us more control over the actions we execute, especially when we are handling large amounts of data.

# Terminal
The terminal is a command line interface that allows users to interact with the operating system by entering text commands.

<p align="center">
    <img src="https://github.com/user-attachments/assets/4572be39-4f92-4bcb-b7a9-7b89991b929d" width="500">
</p>

# Prompt 

The prompt is the text that appears in the console to indicate that the system is ready to receive a command line input.

```bash
ebduran@LAPTOP-IFTA3VOI:~$
```
1. **`ebduran`** is the user.
2. **`@LAPTOP-IFTA3VOI`** is the name of the PC or the IP address of a server.
3. **`~$`** is the current directory we are in, typically the home directory.

# Organization of Unix or Linux
The Linux operating system has a unique structure and organization as shown in the following image:

<p align="center">
    <img src="https://github.com/user-attachments/assets/c614825f-f2da-4d58-b515-32c7583473a2" width="500">
</p>

1. */*: Root of the file system.

2. */bin*: Essential binary files.

3. */etc*: Configuration files.

4. ***/home***: Personal directories of users, where we will work.

5. */var*: Variable files like logs.

6. */usr*: User files (programs and documentation).

# Basic Command Line
We are going to learn how to use the most basic Linux commands so that we can navigate between directories, folders, and manage files (create, move, delete, and copy). Note that most commands are abbreviations in English of the actions we are indicating.
## pwd
**pwd** (print working directory) is the command that allows us to know the path we are in. This command is useful to verify our path to a specific file.

<p align="center">
    <img src="https://github.com/user-attachments/assets/62a287a3-6006-4918-8368-60ddae9976c2" width="500">
</p>

As we can see in the image, I am in my *home* directory under the user *ebduran*.


## ls
**ls** (list) is a command that allows us to list the files and directories in the path where we are located. This command is useful to verify the files we have in each folder, similar to how in Windows we enter a folder and see the files inside it.

<p align="center">
    <img src="https://github.com/user-attachments/assets/0358f54f-0ff2-4c48-b32e-5c7abf975bd7" width="500">
</p>

As we can see in the image, I listed the files in **ebduran** using ***ls***. In this case, I have two folders named ***Documentos*** and ***miniconda3***.

Within each command, there can be arguments (written as -argument) to provide specific or complementary instructions for a command. For the **ls** command, the most commonly used arguments are:
1. **ls -l**: Displays the list in long format, which includes permissions, number of links, owner, group, size, and modification date.

  
<p align="center">
    <img src="https://github.com/user-attachments/assets/f98419e4-e373-4014-bbaf-beacdce340dd" width="500">
</p> 

2. **ls -lh**: Displays the file sizes in KB, MB, GB. In this case, we are combining the -l and -h arguments to have the -lh argument.


<p align="center">
    <img src="https://github.com/user-attachments/assets/c4053cc3-13b6-45e5-a762-fa6ed688edcf" width="500">
</p> 

Do you see the differences between `-l` and `-lh`?

3. To see all possible arguments for each command, we can use **-help**, which prints all the possible arguments. For the **ls** command, it is shown in the following image.

<p align="center">
    <img src="https://github.com/user-attachments/assets/8d556a8a-b252-47ab-a06e-fbe86266c570" width="500">
</p> 

## mkdir

**mkdir** (make directory) is a command that allows us to create directories, similar to how we create folders in Windows. We will use this command often to organize all our files. To create a directory, we need to enter the command followed by a space and the name of the directory to be created.


```bash 
ebduran@LAPTOP-IFTA3VOI:~$ mkdir directory01
```

In this case, we created the directory ***directory01***. If we want to create multiple directories at the same time, each directory name should be separated by spaces:

```bash
ebduran@LAPTOP-IFTA3VOI:~$ mkdir directory02 directory03
```



   


   



