Una shell es un intérprete de comandos interactivo, provee estructuras de control para programar **scripts**.
>[!tip] ¿Qué es un script?
>es un **archivo de texto** que contiene una **secuencia de comandos** que se ejecutan automáticamente por un intérprete de línea de comandos del sistema operativo (_shell_, como Bash en Linux).
## ¿Qué utilidad tiene un shell script?
Nos permite autimatizar tareas, realizar aplicaciones interactivas y hasta aplicaciones con interfaz gráfica(zenity)
## Tipos de shell
Existen varias, la diferencia radica en la sintaxis, en esta materia la que usamos es bash, las más conocidas son:
- sh : Shell por defecto de unix
- bash: la más utilizada en todas las distros
- dash
- csh
>[!note] Ventajas ante otros lenguajes
>Resulta más práctico para manejar archivos, crear procesos y manipular sus salidas. Es independiente de la plataforma, funcionando en cualquier S.O y se puede probar en el intérprete interactivo.
>Es:
> -Interpretado
> -Tipado dinámico y débil

>[!danger] Diferencia entre shell y bash
>El/la shell es un programa que actúa como interfaz entre el usuario y sistema operativo.
>Bash es un tipo específico de Shell.
## Elementos del lenguaje

### Instrucciones
- Internos : los built in
- Externos : archivos separados ????
### Estructuras de control
- if
- while
- for (2 tipos)
- case
### Variables
bash solo soporta strings y arrays. Los nombres son sensibles a las mayúsculas.
#### Creación
```bash
NOMBRE=¨pepe¨ # sin espacios alrededor del =
```
#### Acceso
Para evitar ambigüedades se pueden usar llaves:
``` bash
# Accede a $NOMBRE
echo ${NOMBRE} bienvenido al sistema
```
>[!danger] Restricciones
>Los nombres de las variables pueden contener mayúsculas, minúsculas, números y el símbolo _, pero no pueden empezar con un número

### Arreglos
#### Operaciones
```bash
#crear un arreglo vacío
arreglo_a=() 
# crear un arreglo con valores
arreglo_b=(1 2 3)
# asignación
arreglo_b[2]=spam
# acceso (llaves OBLIGATORIAS!!!!)
echo ${arreglo_b[2]}
copia=${arreglo_b[2]}
# acceso a todos los valores
echo ${arreglo[*]}
# Tamaño del arreglo IMPORTANTE EL #!!!!
${#arreglo[*]}
# Borrado de un elemento (lógico)
unset arreglo[2]
```
>[!danger] Indices
>Los indices de los arreglos comienzan en 0
### Comillas
Tipos de comillas:
- Comillas dobles (¨): Permiten usar el $var y resultados de comandos $(ls)
- Comillas simples (´): No permite lo anterior!!!
>[!tip] No hacen falta, a menos que:
>El string tenga espacios,
>Que sea una variable cuyo contenido puede tener espacios
>Se usen condiciones en las estructuras de control

## Exámen

| job | lle | cpu |
| --- | --- | --- |
| 1   | 0   | 4   |
| 2   | 2   | 9   |
| 3   | 3   | 12  |
**RR q=3**





### Funciones

>[!note] Además
>Se cuenta con las redirecciones y los pipes. Los comentarios empiezan con #

## Comandos muy útiles
```bash
cat archivo
echo ¨hola mundo¨
read var #lee una línea desde entrada estándar en la variable var

# Quedarme con la primer columna d eun texto separado por: desde entrada estandar
cut -d: -f1
#Contar la cantidad de líneas que se leen desde entrada estándar
wc -l

#buscar todos los archivos que contengan la cadena pepe en el directorio /tmp
grep pepe /tmp/*

#buscar todos los archivos dentro del home del usuario, cuyo nombre terminen en .doc
find $HOME -name ¨*.doc¨

# Buscar todos los archivos dentro del directorio actual que sean enlaces simbolicos
find . -type l
```
### Empaquetar y comprimir usando tar
```shell
tar -cvzf archivo.tar.gz arch1 arch2 arch3

tar -xvzf archivo.tar.gz


## Poner mejores ejemplos
```
>[!tip] ¿Archivos zip?
>Usar los comandos unzip 
#### Argumentos útiles del tar

| **Opción** | **Comando Principal** | **Función**                                                                                                                                | **Uso Común (Ejemplo)**            |
| ---------- | --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------- |
| **`-c`**   | **C**rear             | Crea un nuevo archivo `.tar` (un _tarball_).                                                                                               | `tar -cvf archivo.tar /directorio` |
| **`-x`**   | E**x**traer           | Extrae los archivos de un archivo `.tar` existente.                                                                                        | `tar -xvf archivo.tar`             |
| **`-f`**   | **F**ichero           | Indica que el siguiente argumento es el **nombre del archivo** (`.tar` o `.tar.gz`, etc.) con el que se va a trabajar. **Siempre se usa.** | `tar -cvf archivo.tar`             |
| **`-v`**   | **V**erbose           | Muestra una salida detallada, listando los archivos mientras se procesan. Útil para verificar.                                             | `tar -cvf archivo.tar ...`         |
| **`-t`**   | **T**abla/Lista       | Muestra el **contenido** del archivo `.tar` sin extraerlo.                                                                                 | `tar -tvf archivo.tar`             |
#### Argumentos de compresión
|**Opción**|**Compresor**|**Extensión Típica**|
|---|---|---|
|**`-z`**|**gzip**|`.tar.gz` o `.tgz`|
|**`-j`**|**bzip2**|`.tar.bz2` o `.tbz`|
|**`-J`**|**xz**|`.tar.xz`|
## Redirecciones y pipes
Los procesos normalmente cuentan con 3 archivos abiertos
- **sdin** : Entrada estándar, valor 0
- **sdout** : Salida estándar, valor 1
- **stderr** : Salida de error estándar, valor 2
### Redirecciones
```bash
# Redirección destructiva
ls -l > listado.txt 
# Redirección no destructiva (append)
ls -l >> listado.txt
# Redirección de error
ls 2> listado.txt
#Archivo como entrada a comando
cat < archivo #Ejemplo absurdo, buscar uno mejor
```
### Pipes
Conectan la salida de un comando con la entrada de otro, muy útiles para los scripts
```bash
#Sintaxis
comando | comando2 | comando3

#Este comando toma el contenido de un archivo y lo convierte completamente a **mayúsculas**.
cat archivo | tr a-z A-Z
# Este comando busca líneas que contengan la palabra "**hola**" dentro del archivo y luego extrae **solo la primera columna** de esas líneas, asumiendo que las columnas están separadas por una coma (`,`).
cat archivo | grep hola | cut -d, -f1

```