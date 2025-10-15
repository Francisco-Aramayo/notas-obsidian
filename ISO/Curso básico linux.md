## Comandos esenciales
- pwd : imprime el directorio en el que nos encontramos
- ls : lista los directorios, se utiliza con modificadores
- cd : cambiar directorio
- clear : limpiar terminal (Atajo : CTRL + L)
>[!tip] Navegar entre directorios
>Utilizamos el cd. Para volver atrás se usa .. y para el home ~
>se escriben rutas absolutas como relativas

>[!tip] Modificadores
>Casi todos los comandos traen modificadores, pudiendo combinar varios según la salida que deseemos.
>Ejemplo : ls -lha (listar más información, en formato legible y incluir archivos ocultos)

>[!note] Comodines
>se utiliza un * y dependiendo de si ponemos antes o después la cadena de texto, filtra por los que empiecen o terminen. Hay mucha profundidad sobre los comodines, pero con saber esto al principio está más que bien

## Manipular archivos y directorios
- mkdir : crear directorios (se pueden crear muchos a la vez)
- rmdir : eliminamos el directorio (debe estar vacío!)
- touch : crear archivos vacíos y cambiar marcas de tiempo
- cat : podemos mostrar en pantalla el contenido de un archivo, o también crear archivos
- cp: copiar archivos
- rm : borrar archivos
- mv : mover archivos (se pueden mover muchos archivos/ directorios utilizando rutas relativas/absolutas)

>[!tip] Crear archivos con cat
>cat > readme.txt (hasta que no presionemos ctrl + d no para de añadir caracteres al archivo)
>cat readme.txt (mostraría el contenido)

>[!danger] Eliminar directorios o archivos de manera forzada
>rm -rf (r de recursivo y forzar)

## Permisos
- whoami : indica que usuario somos
- id : identidad del usuario (uid, gid, grupos, sudo, etc)
- su : cambiar de usuarios
- adduser : crear usuarios (requiere sudo)
- chmod : cambio de modos o permiso, solo lo puede cambiar el propietario del archivo o el super usuario. Se usa numeración octal o representación simbólica.

>[!tip] Añadir permisos sudo a un usuario 

```bash
fran@debian:~$ ls -l
total 44
drwxr-xr-x 7 fran fran 4096 oct 10 20:42 Descargas
drwxr-xr-x 3 fran fran 4096 oct  2 08:25 Documentos
drwxrwxr-x 5 fran fran 4096 sep 25 15:00 eclipse-workspace
drwxr-xr-x 2 fran fran 4096 oct  9 10:49 Escritorio
drwxr-xr-x 3 fran fran 4096 ago 13 10:30 Imágenes
drwxrwxr-x 3 fran fran 4096 ago 13 11:06 Juegos
drwxr-xr-x 2 fran fran 4096 ago 12 22:21 Música
drwxrwxr-x 9 fran fran 4096 sep 13 13:09 Notas-Obsidian
drwxr-xr-x 2 fran fran 4096 ago 12 22:21 Plantillas
drwxr-xr-x 2 fran fran 4096 ago 12 22:21 Público
drwxr-xr-x 2 fran fran 4096 ago 12 22:21 Vídeos

```
### Primeros 10 caracteres

| Tipo de archivo | Propietario | Grupo | Otro |
| --------------- | ----------- | ----- | ---- |
| -               | rwx         | r--   | ---  |
| d               | rwx         | r-x   | r-x  |
| l               | rwx         | rwx   | rwx  |
#### Tipo de archivo
- - : Archivo normal
- d : Directorio
- l : enlace simbólico, siempre iguales porque los verdaderos permisos están en el original
#### r-w-x

| Atributo | Archivo                                                                                                                                                                          | Directorios                                                                                                             |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| r        | Permite que sea abierto y leído                                                                                                                                                  | Permite que el contenido sea listado si el atributo de ejecución también está configurado                               |
| w        | Permite que sea  escrito, este atributo no permite renombrar o borrar archivos. La capacidad de borrar o renombrar archivos viene determinada por los atributos del directorio.  | Permite crear, borrar y renombrar archivos dentro de un directorio si el atributo de ejecución también está establecido |
| x        | Permite que sea tratado como un programa y ejecutarlo. Los archivos de programas escritos en lenguajes script  deben ser también configurados como legibles para ser ejecutados. | Permite entrar en el directorio usando cd                                                                               |
#### Notación simbólica

| Simbolo | Significado                                    |
| ------- | ---------------------------------------------- |
| u       | Usuario, se refiere al propietario del archivo |
| g       | El grupo del propietario                       |
| o       | Otros                                          |
| a       | Todos = u+g+o                                  |
La operación es + / - seguido por los permisos (rwx)

## Procesos | Como monitorearlos y administrarlos
Cuando iniciamos la computadora, se inicia el kernel, el núcleo del sistema operativo.
Se encarga de permitirle al software el acceso seguro al hardware.
El primer proceso es el systemd, con PID 1
### comando ps
Con ps -e visualizamos todos los procesos corriendo

| PID                       | TTY                              | Time                                   | CMD                    |
| ------------------------- | -------------------------------- | -------------------------------------- | ---------------------- |
| Identificador del proceso | Terminal que controla el proceso | Tiempo que lleva ejecutando el proceso | Comando que lo disparó |
Con ps -aux se agregan las siguientes columnas

| USER    | %CPU       | %MEM           | VSZ                       | RSS                                            | STAT               | START                          |
| ------- | ---------- | -------------- | ------------------------- | ---------------------------------------------- | ------------------ | ------------------------------ |
| Usuario | Uso de cpu | Uso de memoria | Tamaño de memoria virtual | Cantidad de memoria física (RAM) que usa en kb | Estado del proceso | Hora en que comenzo el proceso |
#### Estados del proceso
- R : Running, funcionando
- S : Sleeping, Durmiendo
- D : Esperando E/S
- T : Parado
- Z : Extinto o Zombie
- < Alta prioridad
- N baja prioridad
>[!tip] Top/Htop
Con ps solo obtenemos una instantánea, para monitorear en tiempo real usar el comando top.

### Comando kill
Matamos a un proceso, por su PID

## E/S estándar, Redirecciones y el comando find
Breve explicación de lo que es la E/S estándar
Mencionar la salida de tipo error (sterr)
File descriptors

>[!tip] Ejemplo 

### Redireccionar entrada y salida >< 

### Comando find
- -name
- -size
- +/-

### Tuberías |
