# Linux práctica básica
## Instalación de Ubuntu en Windows
La mayoría de los integrantes del laboratorio de Marine Biogenomics utilizamos Windows como sistema operativo, por lo que debemos utilizar el subsitiema linux con una distribución Linux (GNU/Linux), conocida coloquialmente como "distro". Los usuarios Mac no necesitan de una distro ya que su terminal ya tiene GNU/Linux nativo. Para instalar Ubuntu como distro en Windows, debemos ir a la Microsoft Store, escribir "Ubuntu" en el buscador, seleccionar e instalar la primera opción como se muestra en la figura.

<p align="center">
    <img src="https://github.com/user-attachments/assets/d0a2795d-4718-4c68-ad5f-8cb416849882" width="500">
</p>

# Problemas comunes
Si al abrir  la aplicación te sale el error siguiente:
```bash
Installing, this may take a few minutes...
WslRegisterDistribution failed with error: 0x8007019e
Error: 0x8007019e The Windows Subsystem for Linux has not been enabled.

Press any key to continue...
```
Tienes que dirigirte al buscador de window escribir Windows Powershell para entrar al shell de windows, luego escribir el diguiente comando

```bash
wsl --install
```
Esto te instalará el subsistema para windows. Una vez terminada la instalación debes reiniciar la máquina personal. Posteriormente abres de nuevo el powershell de windows y escribe:

```
wsl
```
Te descargará las actualizaciones y una vez terminadas ya puedes entrar a la aplicación de ubuntu. Deberías de ver tu sheel de linux como al siguiente imagen:


<p align="center">
    <img src="https://github.com/user-attachments/assets/bff1f5d8-4916-4d23-ab3d-2f878b58a1f1" width="500">
</p>


## Un poco de Linux
**¿Por qué utilizamos linux en bioinformática?**. En primer lugar la mayoría de las herramnientas bioinformáticas fueron diseñadas y optimizadas en Linux, ejemplos como BWA, Bowtie, entre otras herramientas. Segundo, Linux es seguro por los permisos y control de accesos que se cnfiguran  dentro del sistema. Tercero, es estable por lo que no hay necesidad de estar actualizando el sistema operativo periódicamente como en windows. Finalmente, es de código abierto por lo que disminuye costos donde no hay que pagar por por los programas, aumenta la oportuinidad de colaboración y hace que cada herramienta sea trasnparete  ya que podemos ver el código fuente. 
En linux vamos a estar trabajando con línea de comandos ya que no hay interfaces gráficas para varias de las herramientas que se utilizan en bioinformática. Una linea de comandos permite dar instrucciones específicas para realizar tareas, esto es importante poque podemos tener más control de las acciones que ejecutamos, especialmente cuando estamos manejando una gran cantidad de datos. 

## Prompt 

El promt es es el texto que aparece en la consola para indicar que el sistema está listo para recibir un comando como se muestra la siguiente imagen:

