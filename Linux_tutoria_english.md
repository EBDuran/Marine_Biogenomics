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
