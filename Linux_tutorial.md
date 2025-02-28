# Linux práctica básica
## Instalación de Ubuntu en Windows
La mayoría de los integrantes del laboratorio de Marine Biogenomics utilizamos Windows como sistema operativo, por lo que debemos utilizar el subsitiema linux con una distribución Linux (GNU/Linux), conocida coloquialmente como "distro". Los usuarios Mac no necesitan de una distro ya que su terminal ya tiene GNU/Linux nativo. Para instalar Ubuntu como distro en Windows, debemos ir a la Microsoft Store, escribir "Ubuntu" en el buscador, seleccionar e instalar la primera opción como se muestra en la figura.

<p align="center">
    <img src="https://github.com/user-attachments/assets/d0a2795d-4718-4c68-ad5f-8cb416849882" width="500">
</p>

## Problemas comunes
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


# Un poco de Linux
**¿Por qué utilizamos linux en bioinformática?**. En primer lugar la mayoría de las herramnientas bioinformáticas fueron diseñadas y optimizadas en Linux, ejemplos como BWA, Bowtie, entre otras herramientas. Segundo, Linux es seguro por los permisos y control de accesos que se cnfiguran  dentro del sistema. Tercero, es estable por lo que no hay necesidad de estar actualizando el sistema operativo periódicamente como en windows. Finalmente, es de código abierto por lo que disminuye costos donde no hay que pagar por por los programas, aumenta la oportuinidad de colaboración y hace que cada herramienta sea trasnparete  ya que podemos ver el código fuente. 
En linux vamos a estar trabajando con línea de comandos ya que no hay interfaces gráficas para varias de las herramientas que se utilizan en bioinformática. Una linea de comandos permite dar instrucciones específicas para realizar tareas, esto es importante poque podemos tener más control de las acciones que ejecutamos, especialmente cuando estamos manejando una gran cantidad de datos. 

# Terminal
La terminal es una interfaz de línea de comandos que permite a los usuarios interactuar con el sistema operativo mediante la introducción de comandos de texto.

<p align="center">
    <img src="https://github.com/user-attachments/assets/4572be39-4f92-4bcb-b7a9-7b89991b929d" width="500">
</p>

# Prompt 

El promt es es el texto que aparece en la consola para indicar que el sistema está listo para recibir una línea de comando:
```bash
ebduran@LAPTOP-IFTA3VOI:~$
```
1. *`ebduran`* es el usurario
2. *`@LAPTOP-IFTA3VOI`* es el nombre de la PC o dirección IP de algún servidor
3. *`~$`*  el directorio actual en el que nos encontramos, normalmente es el home 

# Organización de Unix o linux 
El sistema operativo de Linux tiene una estructura y organización única como se muestra en la imagen siguiente:

<p align="center">
    <img src="https://github.com/user-attachments/assets/c614825f-f2da-4d58-b515-32c7583473a2" width="500">
</p>

1. *`/`*: Raíz del sistema de archivos.

2. *`/bin`*: Archivos binarios esenciales.

3. *`/etc`*: Archivos de configuración.

4. ***`/home`***: Directorios personales de los usuarios, es donde vamos a trabajar

5. *`/var`*: Archivos variables como logs.

6. *`/usr`*: Archivos de usuario (programas y documentación).

# Línea de comandos basicos
Vamos a aprender a utilizar los comando más básiscos de linux para que podamos movernos entre direcrtorios, carpetas y gestionar archivos (crear, mover, eliminar y copiar), notar que la mayoría de los comandos son abreviaciones en inglés de acciones que estamos indicando.
## pwd (print working directory)
**`pwd`**  es el comando que nos permite conocer la ruta en la que nos encontramos. Este comando es útil para verificar nuestra ruta de un archivo especíca.

<p align="center">
    <img src="https://github.com/user-attachments/assets/62a287a3-6006-4918-8368-60ddae9976c2" width="500">
</p>

Como podemos ver en la imagen estoy en mi *home* dentro del usuario *ebduran*

## ls (list)
**`ls`**  es un comando que nos permite enlistar los archivos y directorios que estén en la ruta donde nos encontramos. Este comando es útil apra verificar los archivos que tenemos en cada carpeta, algo así como en windows cuando entramos a una carpeta y ya vemos los arvhivos denrtro de la misma. 

<p align="center">
    <img src="https://github.com/user-attachments/assets/0358f54f-0ff2-4c48-b32e-5c7abf975bd7" width="500">
</p>

Como podemos ver en la imagen enlisté con ***ls*** los archivos que tengo en **ebduran**, en este caso tengo dos carpetas que se llaman ***Documentos*** y ***miniconda3***. 

Dentro de cada comando pueden existir argumentos  (se escribe -el argumento) para dar instrucciones de acciones complementarias o específicas de un comando, para el caso de **ls**, las más usadas son:
1. **`ls -l`**: Muestra la lista en formato largo, que incluye permisos, número de enlaces, propietario, grupo, tamaño y fecha de modificación.
  
<p align="center">
    <img src="https://github.com/user-attachments/assets/f98419e4-e373-4014-bbaf-beacdce340dd" width="500">
</p> 

2. **`ls -lh`** Muestra los tamaños de los archivos en KB, MB, GB, en este caso estamos combinando -l y h para tener el argumento -lh

<p align="center">
    <img src="https://github.com/user-attachments/assets/c4053cc3-13b6-45e5-a762-fa6ed688edcf" width="500">
</p> 

ven las diferencias entre -l y -lh?

3. Para ver todos los argumentos posibles de cada comando podemos utilizar **-help**, el cual nos imprime todos los argumentos posibles, para el caso de **ls** se muestra en la siguient imagen.

<p align="center">
    <img src="https://github.com/user-attachments/assets/8d556a8a-b252-47ab-a06e-fbe86266c570" width="500">
</p> 

## mkdir (make directory)

**`mkdir`**  es un comando que nos permite crear directorios, como cuando en windows creamos carpetas. Este comando lo vamos a utilizar mucho para organizar todos nuestros archivos. Para crear un directorio debemos poner el comando un espacio y el nombre del direcotrio a crear, hagámoslo para crear un directorio que se llame `directory01`

```bash 
mkdir directory01
```
En este caso creamos el directorio ***directory01***, si queremos hacer varios directorios, cada uno de ellos debe estar separado por espacios:

```bash
mkdir directory02 directory03
```
Si hacemos un list ¿cúantos directorios tenemos?

## Rutas

En linux es importante movernos entre directorios, por lo que nosotros podemos morvernos entre rutas con línea de comando, para ello hay dos maneras:
1. Ruta absoluta
2. Ruta relativa

La **Ruta absoluta** es una dirección completa y específica que indica la ubicación exacta de un archivo o directorio. Las rutas absolutas siempre comienzan desde el directorio raíz, que se representa con una barra diagonal hacia adelante `/` y termina con el destino final. **No importa desde qué ubicación estés trabajando, una ruta absoluta siempre te llevará a la misma ubicación que proporcionas**.

Un ejemplo de ruta absoluta para llegar al directortio llamado `work` de la imagen de abajo es:

 ```bash 
 /home/peter/work
```

<p align="center">
    <img src="https://github.com/user-attachments/assets/9a5fa948-7938-47ba-bee2-229129e7b58a" width="500">
</p> 

Una **ruta relativa** indica la ubicación de un archivo o directorio **en relación con el directorio actual en el que te encuentras trabajando**. A diferencia de una ruta absoluta, que comienza desde el directorio raíz `/`, una ruta relativa comienza desde la ubicación actual representada con `.` o desde el directorio padre o superior `..`, si quieres moverte hacia una carpeta superior del padre de donde te encuetras ubicado, debes utilizar los seaparadores  de directorios ``../..``. En la siguiente imagen se muestran las rutas relativas desde el directorio ``peter``


<p align="center">
    <img src="https://github.com/user-attachments/assets/7440ea92-3de9-4cfc-992e-dd9097e4716c" width="500">
</p> 

Si quieres ir desde  ``peter`` a ``home`` el comando es:

``..
``

si quieres ir desde ``peter`` que es ``.`` a papers es:

``./papers
``

## cd (change directory) 
**`cd`** este comando nos permite cambiar de directorios. Puedes moverte a un directorio específico con rutas absolutas o relativas. Por el momento estamos en el directorio del usuario en mi caaso ebduran. Si nos queremos mover al directorio directory01 podemos utilizar el comando `cd` , espacio y el nombre del directorio objetivo.

``` bash
cd directory01
```

**Consejo**: siempre que vayas entrar a una carpeta en lugar de escribirla completamente, escribe las primeras letras y utiliza la tecla `TAB` para autocompletar el nombre. 


Si nos queremos regresar al directorio de mi usuario debemos utilizar `cd ..`  ya que es el directorio superior a directory01 o tambien puedes escribir la ruta absoluta `cd /home/ebduran`.

``` bash
cd ..
```

Otros atajos que son importantes:

`cd ~` Te lleva al directorio de inicio del usuario en mi caso a /home/ebduran.

`cd /` Te lleva al directorio raíz del sistema.

En que directorio estamos actualmente?

## mv (move/rename)
El comando `mv` nos ayuda a mover archivos de un directorio a otro. Tambien sirve para renombar directorios o archivos.
Para mover los archivos debemos escribir `mv`  epacio `el documento a mover`, espacio y  el directorio al cual quieres mover, ya sea con ruta absoluta o relativa.

1. Para renombrar: Vamos a renombrar el directorio `directory01` con el nombre de `reference_genome`, como ven en lugar de espacios separa las palabras con `_`.

```bash
mv directory01 reference_genome
```
2. Mover documento: Por el momento no tenemos ningun archivo, pero para mover archivos debes poner la siguiente línea de comando

``` bash
mv tu_archivo destino(en ruta absoluta o relativa)
```
   
## wget (World Wide Web" y "get")

`wget` es un comando que nos permite descargar archivos de la web utilizando un URL(Uniform Resource Locators). Este comando es útil porque podemos descargar las secuencias desde NCBI. Vamos a descargar la secuencia del genoma de referencia de un simbionte coralino en el directorio que creamos llamada `reference_genome`.
Recuerden ver donde estamos (ya lo vimos) y como entrar al directorio `reference_genome`.

```bash
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/001/939/145/GCA_001939145.1_ASM193914v1/GCA_001939145.1_ASM193914v1_genomic.fna.gz
```
Esto tardará unos minutos. Si todo salió bien tendremos el genoma de referencia de *Symbiodinium microadriaticum* desde NCBI. Una vez descargado vean cual es el tamaño del archivo (ya lo vimos anteriormente).

Repitamos el comando `wget` pero esta vez vamos a descargar otro genoma de referencia de *Cladocopium goreaui*, también vamo a utilizar el argumento `-0` que nos permite cambiar el nombre del archivo descargado, por lo que vamos a cambiar el nombre a `cladocopium_genome.fna.gz ` 

```bash
wget -O cladocopium_genome.fna.gz https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/947/184/155/GCA_947184155.2_Cgoreaui_SCF055-01_v2.1/GCA_947184155.2_Cgoreaui_SCF055-01_v2.1_genomic.fna.gz
```

Ahora tenemos dos genomas de referencia de simbiontes de corales, pero el nombre del archivo de *Symbiodinium microadriaticum* es muy largo, entonces cambiemos el nombre a `simbiodinium_genome.fna.gz` ya saben como. Utilicen `TAB` para poder completar el nombre automáticamente.


## descomprimir con gunzip

Los genomas de referencia están comprimidos por eso tienen la terminación `.gz`. Hay que descomprimirlos para ver su contenido con el comando `gunzip` y el documento a descomprmir. En este caso vamos a descomprimir `simbiodinium_genome.fna.gz`

```bash
gunzip simbiodinium_genome.fna.gz
```
Una vez terminado, checar el tamaño del documento descomprimido (ya sabemos como). Hacer lo mismo con el archivo `cladocopium_genome.fna.gz`

## cat para concatenar documentos

`cat` es un comando que nos permite concatenar documentos. En esta ocasión vamos tambien a utilizar `>` que nos permite redireccionar en un nuevo archivo el contendido de la concatenación. En este caso vamos a concatenar los documentos descomprimidos de los genomas de referencia y el contenido será redireccionado a un documento que se llame `symbion_genome_concatenade.fna` con la siguiente comando:

```bash
cat  simbiodinium_genome.fna cladocopium_genome.fna > symbiont_genome_concatenade.fna

```

## cp (Copy)

Ahora vamos copiar el archivo `symbiont_genome_concatenade.fna` en otra carpeta con el comando `cp`, nos movemos al directorio del usurario, cambiamos el nombre de `directory02` a `genome_conatenade` y entramos a la carpteta, ahora copiamos el archivo que esta en `/home/userxx/reference_genome/symbiont_genome_concatenade.fna` con el siguiente comando, cambien su usurario!!!

```bash
cp /home/userxx/reference_genome/symbiont_genome_concatenade.fna ./
```
Enlistamos y si vemos el archivo la copia fue un exito. Como notarán utilizamos una ruta absoluta, ¿cómo sería con una ruta relativa?

## Ver el contenido de cada 
### Less
El comando `less` se utiliza para visualizar el contenido de archivos de texto de manera interactiva, permitiéndote desplazarte hacia arriba y hacia abajo a través del archivo. Vamos a revisra el archivo `symbiont_genome_concatenade.fna` con el siguiente comando:

```bash
less symbiont_genome_concatenade.fna
```
Debemos ver algo similar a esto:

<p align="center">
    <img src="https://github.com/user-attachments/assets/980e47aa-5790-4c7b-978b-ac230ec34636" width="500">
</p>

Podemos desplazarnos con las flechas del tecldo hacia arriba y abajo
Para salir del texto debemos utilizar `q`

### head 
`head`  se utiliza para mostrar las primeras líneas de un archivo de texto. Por defecto, head muestra las primeras 10 líneas del archivo especificado. Veamos las primeras 10 líneas del archivo `symbiont_genome_concatenade.fna`

```bash
head symbiont_genome_concatenade.fna
```

<p align="center">
    <img src="https://github.com/user-attachments/assets/3b02ca7e-9194-4c24-b4a0-0ff06d7e4ecf" width="500">
</p>

### tail
`head`  se utiliza para mostrar las ultimas líneas de un archivo de texto. Por defecto, head muestra las primeras 10 líneas del archivo especificado. Veamos las últimas 10 líneas del archivo `symbiont_genome_concatenade.fna`

```bash
tail symbiont_genome_concatenade.fna
```

<p align="center">
    <img src="https://github.com/user-attachments/assets/5e4b8a85-f721-4fa0-bd59-58d0df7a0eae" width="500">
</p>

Tanto para `head` y `tail` podemos seleccionar el número de lineas que queremos observar con el argumento `-n` y el número de líneas que quieres ver. Veamos un ejemplo con `head`.

``` bash
head -n 2  symbiont_genome_concatenade.fna
```
Esto es lo que se muestra en la terminal:

<p align="center">
    <img src="https://github.com/user-attachments/assets/b7a4a43b-ff35-40c4-8d3d-251ae571d343" width="500">
</p>

Ahora juguemos con el tail utilizando diferentes números de lines con `-n`.

# Fin del primer tutorial para comandos de linux, gracias por su atención!







   


   


