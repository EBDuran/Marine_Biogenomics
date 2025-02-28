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

## Paths

In Linux, it is important to move between directories, so we can navigate paths using the command line in two ways:

1. Absolute Path

2. Relative Path

An **Absolute Path** is a complete and specific path that indicates the exact location of a file or directory. Absolute paths always start from the root directory, represented by a forward slash `/`, and  the final destination. **No matter where you are working from, an absolute path will always take you to the provided location**.

An example of an absolute path to reach the directory named work in the image below is:
 ```bash 
 /home/peter/work
```

<p align="center">
    <img src="https://github.com/user-attachments/assets/9a5fa948-7938-47ba-bee2-229129e7b58a" width="500">
</p> 

A **Relative Path** indicates the location of a file or directory **in relation to the current directory you are working in**. Unlike an absolute path, which starts from the root directory `/`, a relative path starts from the current location represented by `.` or from the parent or upper directory `..`. If you want to move to a higher folder from where you are located, you need to use directory separators `../..`. In the following image, the relative paths are shown from the directory peter.

<p align="center">
    <img src="https://github.com/user-attachments/assets/7440ea92-3de9-4cfc-992e-dd9097e4716c" width="500">
</p> 

If you want to go from `peter` to `home` the command is:

``..
:

``..
``

If you want to go from `peter`, which is represented by `.`, to papers, the command is:

``./papers
``

## cd (change directory) 

**`cd`** this command allows us to change directories. You can move to a specific directory using absolute or relative paths. Currently, we are in the user's directory, in my case ebduran. If we want to move to the directory directory01, we can use the `cd` command, space, and the target directory name.


``` bash
cd directory01
```

**Tip**: whenever you want to enter a folder, instead of typing the entire name, type the first few letters and use the `TAB` key to autocomplete the name.

If we want to return to my user's directory, we should use `cd ..` because it is the parent directory of directory01, or you can also write the absolute path `cd /home/ebduran`.

``` bash
cd ..
```

Other important shortcuts:

`cd ~` Takes you to the user's home directory, in my case to /home/ebduran.

`cd /` Takes you to the root directory of the system.


In which directory are we currently?


## mv (move/rename)
The `mv` command helps us move files from one directory to another. It also serves to rename directories or files.
To move files, we need to type `mv`, space, `the document to move`, space, and the directory to which you want to move it, either with an absolute or relative path.

1. To rename: Let's rename the directory `directory01` to `reference_genome`, using underscores `_` to separate words instead of spaces.

```bash
mv directory01 reference_genome
```

2. To move a document: Currently, we don't have any files, but to move files, you need to use the following command:

``` bash
mv tu_archivo destino(en ruta absoluta o relativa)
```
   
## wget (World Wide Web" y "get")

`wget` is a command that allows us to download files from the web using a URL (Uniform Resource Locators). This command is useful because we can download sequences from NCBI. Let's download the reference genome sequence of a coral symbiont into the directory we created named `reference_genome`.

Remember to check where we are (we have already done this) and how to enter the `reference_genome` directory.

```bash
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/001/939/145/GCA_001939145.1_ASM193914v1/GCA_001939145.1_ASM193914v1_genomic.fna.gz
```
This will take a few minutes. If everything goes well, we will have the reference genome of *Symbiodinium microadriaticum* from NCBI. Once downloaded, check the file size (we have already seen how to do this).

Let's repeat the `wget` command, but this time we will download another reference genome of *Cladocopium goreaui*. We will also use the `-0` argument to change the name of the downloaded file, so we will change the name to `cladocopium_genome.fna.gz`.


```bash
wget -O cladocopium_genome.fna.gz https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/947/184/155/GCA_947184155.2_Cgoreaui_SCF055-01_v2.1/GCA_947184155.2_Cgoreaui_SCF055-01_v2.1_genomic.fna.gz
```

Now we have two reference genomes of coral symbionts, but the file name of *Symbiodinium microadriaticum* is too long, so let's change it to `simbiodinium_genome.fna.gz`. You already know how. Use `TAB` to autocomplete the name automatically.

## Decompressing with gunzip

The reference genomes are compressed, which is why they have the `.gz` extension. We need to decompress them to see their content using the `gunzip` command and the file to decompress. In this case, we are going to decompress `simbiodinium_genome.fna.gz`.


```bash
gunzip simbiodinium_genome.fna.gz
```

Once finished, check the size of the decompressed document (we already know how). Do the same with the file `cladocopium_genome.fna.gz`.

## cat to concatenate files

`cat` is a command that allows us to concatenate files. On this occasion, we will also use `>` to redirect the concatenation content to a new file. In this case, we will concatenate the decompressed reference genome files, and the content will be redirected to a file named `symbion_genome_concatenade.fna` with the following command:


```bash
cat  simbiodinium_genome.fna cladocopium_genome.fna > symbiont_genome_concatenade.fna

```

## cp (Copy)

Now we will copy the file `symbiont_genome_concatenade.fna` to another folder using the `cp` command. We move to the user's directory, rename `directory02` to `genome_conatenade`, and enter the folder. Now we copy the file located at `/home/userxx/reference_genome/symbiont_genome_concatenade.fna` with the following command (make sure to change your username!!!

```bash
cp /home/userxx/reference_genome/symbiont_genome_concatenade.fna ./
```
We list the files and if we see the file, the copy was successful. As you noticed, we used an absolute path. How would it be with a relative path?

## Viewing the Content of Each File
### Less
The `less` command is used to interactively view the content of text files, allowing you to scroll up and down through the file. Let's review the file `symbiont_genome_concatenade.fna` with the following command:

```bash
less symbiont_genome_concatenade.fna
```
We should see something similar to this:

<p align="center">
    <img src="https://github.com/user-attachments/assets/980e47aa-5790-4c7b-978b-ac230ec34636" width="500">
</p>

We can navigate up and down using the arrow keys on the keyboard. 
To exit the text view, we use `q`.

### head 
`head` is used to display the first lines of a text file. By default, `head` shows the first 10 lines of the specified file. Let's see the first 10 lines of the file `symbiont_genome_concatenade.fna`.


```bash
head symbiont_genome_concatenade.fna
```

<p align="center">
    <img src="https://github.com/user-attachments/assets/3b02ca7e-9194-4c24-b4a0-0ff06d7e4ecf" width="500">
</p>

### tail
`tail` is used to display the last lines of a text file. By default, `tail` shows the last 10 lines of the specified file. Let's see the last 10 lines of the file `symbiont_genome_concatenade.fna`.


```bash
tail symbiont_genome_concatenade.fna
```

<p align="center">
    <img src="https://github.com/user-attachments/assets/5e4b8a85-f721-4fa0-bd59-58d0df7a0eae" width="500">
</p>

For both `head` and `tail`, we can select the number of lines we want to observe using the `-n` argument followed by the number of lines you want to see. Let's see an example with `head`.


``` bash
head -n 2  symbiont_genome_concatenade.fna
```

This is what is displayed in the terminal:

<p align="center">
    <img src="https://github.com/user-attachments/assets/b7a4a43b-ff35-40c4-8d3d-251ae571d343" width="500">
</p>

Now let's play with the `tail` command using different numbers of lines with `-n`.

# End of the first tutorial for Linux commands, thank you for your attention!







   


   



   


   



