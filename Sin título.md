# Guía Técnica del Comando : Monitoreo y Gestión de Procesos

### 1.0 Introducción al Comando

El comando `ps` (del inglés _process status_) es una herramienta fundamental en cualquier sistema operativo tipo UNIX, proporcionando una "instantánea" (_snapshot_) de los procesos que se encuentran activos en un momento determinado. Su propósito principal es permitir a los administradores de sistemas y usuarios monitorear qué programas se están ejecutando, quién los ejecuta y qué recursos están consumiendo. A diferencia de herramientas como `top`, que ofrecen una vista dinámica y actualizada en tiempo real, `ps` está diseñado para ofrecer una vista estática y puntual, ideal para diagnósticos específicos, generación de informes y automatización de scripts.

Este comando obtiene su información directamente leyendo los archivos virtuales del directorio `/proc`, que es una interfaz del kernel al espacio de usuario. Gracias a este método, `ps` no requiere privilegios especiales para su ejecución básica, permitiendo a cualquier usuario inspeccionar sus propios procesos sin necesidad de elevación.

Para utilizar `ps` de manera efectiva, es crucial comprender primero los diferentes estilos de sintaxis que acepta. Esta flexibilidad, heredada de múltiples estándares y implementaciones a lo largo de la historia de UNIX, es una de sus mayores fortalezas, pero también una fuente común de confusión. A continuación, desglosaremos estas sintaxis para sentar las bases de un uso correcto y potente del comando.

### 2.0 Comprendiendo la Sintaxis: Opciones UNIX, BSD y GNU

Una de las características más peculiares de `ps` es su compatibilidad con tres estilos de opciones diferentes: UNIX, BSD y GNU. Entender estas distinciones es fundamental, ya que el tipo de opción utilizada no solo cambia el comportamiento del comando, sino que también puede alterar la selección de procesos y el formato de salida por defecto. Aunque es posible mezclar opciones de diferentes tipos, hacerlo sin conocimiento puede generar conflictos o resultados inesperados.

La siguiente tabla resume las características clave de cada estilo:

|   |   |   |
|---|---|---|
|Tipo de Opción|Sintaxis|Características Clave|
|**Opciones UNIX**|`-e`, `-f`|Deben ir precedidas por un guion (`-`). Pueden agruparse en una sola cadena (p. ej., `ps -ef`).|
|**Opciones BSD**|`ax`, `u`|No utilizan guion. Pueden agruparse. Su uso añade la columna `STAT` a la salida por defecto y muestra los argumentos del comando (`args`) en lugar del nombre del ejecutable (`comm`).|
|**Opciones GNU**|`--deselect`, `--help`|Van precedidas por dos guiones (`--`). Son opciones largas y descriptivas, fáciles de recordar.|

Es importante advertir sobre una confusión muy común. Comandos como `ps -aux` son un híbrido problemático. Según los estándares POSIX y UNIX, esta sintaxis se interpreta como "mostrar todos los procesos asociados a una terminal (opción `-a`) más todos los procesos del usuario llamado 'x' (opción `-u x`)". Sin embargo, si el usuario 'x' no existe en el sistema, muchas implementaciones de `ps`, por compatibilidad, asumen que el usuario realmente quiso decir `ps aux` (el estilo BSD). Para evitar ambigüedades, se recomienda utilizar `ps -ef` (estilo UNIX) o `ps axu` (estilo BSD) de forma consistente.

Una vez dominada la sintaxis, el siguiente paso es aprender a utilizar las potentes capacidades de `ps` para seleccionar exactamente los procesos que nos interesan.

### 3.0 Selección de Procesos: Cómo Filtrar lo que Necesitas Ver

La principal fortaleza de `ps` reside en su extraordinaria flexibilidad para seleccionar procesos. En lugar de mostrar una lista abrumadora de todo lo que se está ejecutando, el comando permite aplicar desde filtros muy amplios hasta criterios extremadamente específicos para aislar únicamente los procesos que se necesitan analizar. Se puede seleccionar por usuario, por terminal, por nombre de comando e incluso por relaciones de parentesco entre procesos.

#### 3.1 Selección Simple y General

Estas opciones son de propósito general y cubren los casos de uso más comunes para obtener vistas amplias del sistema.

- `**-e**` **o** `**-A**` Selecciona **todos** los procesos que se están ejecutando en el sistema, sin excepción. Son funcionalmente idénticas.
- `**a**` En la sintaxis BSD, levanta la restricción de "mostrar solo tus propios procesos". Una descripción alternativa es que esta opción lista todos los procesos con una terminal (tty), o bien lista absolutamente todos los procesos si se usa junto con la opción `x`.
- `**-a**` En la sintaxis UNIX, selecciona todos los procesos excepto los líderes de sesión y aquellos que no están asociados a ninguna terminal.
- `**x**` En la sintaxis BSD, levanta la restricción de que un proceso "debe tener una terminal (tty)", permitiendo ver procesos que se ejecutan en segundo plano, como los demonios del sistema. De forma alternativa, se puede describir como la opción que lista todos los procesos de tu propiedad (mismo EUID), o todos los procesos del sistema si se combina con `a`.
- `**r**` Restringe la selección únicamente a los procesos que se encuentran en estado de ejecución (_running_).
- `**T**` Selecciona todos los procesos que están asociados con la terminal actual desde la que se ejecuta el comando `ps`.
- `**-d**` Selecciona todos los procesos del sistema, a excepción de los líderes de sesión.
- `**g**` Lista absolutamente todos los procesos, incluyendo los líderes de sesión. **Nota:** Esta opción está obsoleta y podría ser eliminada en futuras versiones. No se recomienda su uso en scripts o prácticas modernas.

#### 3.2 Selección por Listas Específicas

Para un control granular, `ps` permite filtrar procesos basándose en listas de identificadores específicos, como el ID de proceso (PID), el ID de usuario (UID) o el grupo.

|   |   |   |
|---|---|---|
|Opción|Criterio de Selección|Ejemplo de Uso|
|`**-p**`, `**--pid**`, `**p**`|Por ID de Proceso (PID).|`ps -p 1,123,456`|
|`**--ppid**`|Por ID de Proceso Padre (PPID).|`ps --ppid 1`|
|`**-u**`, `**U**`, `**--user**`|Por ID de Usuario Efectivo (EUID) o nombre.|`ps -u www-data,postgres`|
|`**-U**`, `**--User**`|Por ID de Usuario Real (RUID) o nombre.|`ps -U root`|
|`**-g**`|Por Sesión o por Grupo Efectivo. Selecciona por sesión si la lista es numérica; por nombre de grupo efectivo si se especifican nombres.|`ps -g 115` (sesión)|
|`**-G**`, `**--Group**`|Por ID de Grupo Real (RGID) o nombre.|`ps -G video`|
|`**-C**`|Por nombre del comando (nombre del ejecutable).|`ps -C sshd,nginx`|
|`**-s**`, `**--sid**`|Por ID de Sesión.|`ps -s 1234`|
|`**-t**`, `**--tty**`|Por terminal (tty) asociada.|`ps -t tty1,pts/0`|
|`**-N**`, `**--deselect**`|Invierte la selección, mostrando todos los procesos **excepto** los que cumplen el criterio.|`ps -U root -N`|

Tras haber seleccionado el conjunto de procesos deseado, el siguiente paso es definir qué información queremos visualizar sobre ellos, personalizando completamente la salida.

### 4.0 Control del Formato de Salida: Personalizando la Visualización

Una vez que hemos filtrado los procesos de interés, `ps` nos permite controlar con precisión qué columnas de información se mostrarán. Esta capacidad es crucial para adaptar la salida a la tarea específica que estemos realizando, ya sea un diagnóstico rápido, la generación de un informe detallado o la extracción de datos para un script. El comando ofrece desde formatos predefinidos de uso común hasta una personalización completa columna por columna.

#### 4.1 Formatos Predefinidos Comunes

Estas opciones activan formatos de salida estandarizados que son útiles para diferentes tipos de análisis con solo añadir un flag.

- `**-f**` **(Full Format)** Proporciona un listado de formato completo que incluye UID, PID, PPID, información de uso de CPU y la hora de inicio del proceso. También muestra la línea de comandos completa.
- `**-F**` **(Extra Full Format)** Similar a `-f`, pero añade columnas adicionales con más detalles, como el tamaño del proceso.
- `**l**` **(Long Format BSD)** Activa el formato largo de estilo BSD, que muestra información detallada como flags del proceso (F), estado (S), prioridad (PRI), y el valor "nice" (NI).
- `**-l**` **(Long Format UNIX)** Activa un formato largo de estilo UNIX, similar al BSD pero con algunas diferencias en las columnas mostradas.
- `**u**` **(User-Oriented Format)** Presenta la información orientada al usuario, incluyendo el nombre del usuario propietario, el porcentaje de uso de CPU (`%CPU`) y de memoria (`%MEM`), y el tamaño de memoria virtual (VSZ) y residente (RSS).
- `**j**` **(Jobs Format)** Muestra la información en un formato de control de trabajos (jobs), útil para ver el ID de grupo de proceso (PGID) y el ID de sesión (SID).
- `**s**` **(Signal Format)** Presenta la información en un formato orientado a señales, mostrando el estado de las señales pendientes.

#### 4.2 Formato Definido por el Usuario (, )

La opción `-o` (o su alias `--format`) es la herramienta más potente para personalizar la salida de `ps`. Permite especificar exactamente qué columnas se deben mostrar y en qué orden, utilizando una lista de palabras clave (especificadores de formato) separadas por comas o espacios.

Por ejemplo, para crear una vista personalizada que muestre el PID, el PPID, el usuario, el porcentaje de CPU y memoria, y el nombre del comando, se usaría el siguiente comando:

```bash
ps -eo pid,ppid,user,%cpu,%mem,comm
```

Además, esta opción permite funcionalidades avanzadas como:

- **Renombrar cabeceras:** Se puede cambiar el título de una columna usando el formato `keyword=NUEVO_NOMBRE`. Para evitar ambigüedades y problemas de portabilidad, se recomienda usar una opción `-o` separada para cada columna que se renombra.
- **Controlar el ancho de las columnas:** Se puede definir un ancho específico para una columna añadiendo `:N` después de la palabra clave, donde `N` es el número de caracteres.

Una vez definido el contenido y la estructura de las columnas, podemos refinar aún más la presentación final ajustando el orden de las filas y otros detalles visuales.

### 5.0 Modificadores de Salida: Refinando la Presentación Final

Más allá de seleccionar procesos y definir columnas, `ps` ofrece un conjunto de modificadores que permiten ajustar los detalles finos de la presentación. Estos controles son esenciales para generar informes limpios y legibles, así como para facilitar el procesamiento automático de la salida en scripts. Permiten gestionar desde el orden de los procesos hasta el ancho de la pantalla y la visibilidad de las cabeceras.

#### 5.1 Ordenamiento de Procesos (, )

La opción `--sort` (y su alias `-k`) permite ordenar la lista de procesos según una o más columnas. La sintaxis consiste en una lista de especificadores de formato. Por defecto, el orden es ascendente (`+`), pero se puede especificar un orden descendente anteponiendo un guion (`-`) a la clave de ordenamiento.

- **Ejemplo 1: Ordenar por ID de usuario (ascendente), luego por PPID (descendente) y finalmente por PID (ascendente).**
- **Ejemplo 2: Ordenar todos los procesos por su hora de inicio.**

#### 5.2 Control de Cabeceras y Ancho

Estas opciones ajustan cómo se presentan las cabeceras de las columnas y el ancho total de la salida.

- `**h**` **/** `**--no-headers**` Suprime completamente la línea de cabecera de la salida. Es muy útil cuando la salida de `ps` se va a procesar con otras herramientas como `grep` o `awk`.
- `**--headers**` Repite la línea de cabecera en cada "página" de la salida, lo cual puede ser útil si la lista de procesos es muy larga y se visualiza en la terminal.
- `**w**` **/** `**-w**` Produce una salida ancha. Si se especifica una vez (`-w`), evita el truncamiento de líneas largas. Si se especifica dos veces (`-ww`), el ancho de la salida es ilimitado, mostrando las líneas completas sin importar su longitud.
- `**--cols**` **/** `**--columns**` **/** `**--width**` Permiten establecer un ancho de pantalla específico en número de caracteres. Esto es útil para forzar un formato consistente cuando la salida se redirige a un archivo.

#### 5.3 Jerarquía de Procesos (Árbol)

Para visualizar la relación padre-hijo entre los procesos, `ps` puede generar un "bosque" o árbol de procesos.

- `**f**` **/** `**--forest**` Muestra la jerarquía de procesos utilizando caracteres ASCII para dibujar un árbol, lo que facilita enormemente la comprensión de las relaciones de dependencia.
- `**-H**` Agrupa los procesos y los muestra en un formato jerárquico, similar a `f`.

Con estas herramientas, es posible crear vistas de procesos altamente personalizadas y ordenadas. A continuación, exploraremos capacidades más especializadas de `ps` para escenarios de análisis avanzados.

### 6.0 Capacidades Avanzadas y Casos de Uso Específicos

Además de sus funciones estándar de monitoreo, `ps` incluye opciones para escenarios de análisis más profundos. Estas capacidades permiten inspeccionar componentes internos de los procesos, como los hilos de ejecución (_threads_), o visualizar información de seguridad específica del sistema, como los contextos de SELinux.

#### 6.1 Visualización de Hilos (Threads)

En los sistemas operativos modernos, un solo proceso puede constar de múltiples hilos de ejecución. `ps` proporciona varias opciones para visualizarlos.

|   |   |
|---|---|
|Opción|Descripción del Comportamiento|
|`**H**`|Muestra los hilos como si fueran procesos individuales. Cada hilo aparecerá en una línea separada.|
|`**-L**`|Muestra los hilos, pero añade columnas específicas para ellos, como `LWP` (Light Weight Process ID) y `NLWP` (Number of Light Weight Processes).|
|`**m**` **/** `**-m**`|Muestra los hilos después de su proceso padre correspondiente, ayudando a visualizar la agrupación.|

#### 6.2 Visualización de Información de Seguridad (SELinux)

En sistemas que utilizan mecanismos de control de acceso obligatorio como SELinux, es crucial poder ver el contexto de seguridad en el que se ejecuta cada proceso.

- `**-M**` **o** `**Z**` Estas opciones, que son funcionalmente idénticas, añaden una columna de datos de seguridad a la salida. Esta columna muestra el "label" o contexto de seguridad del proceso, siendo una herramienta indispensable para la depuración de políticas de SELinux.

Para consolidar todo el conocimiento adquirido, la mejor manera es verlo en acción. La siguiente sección presenta una serie de ejemplos prácticos que resuelven tareas comunes de administración de sistemas.

### 7.0 Ejemplos Prácticos

A continuación se presentan una serie de "recetas" prácticas que demuestran cómo combinar las opciones de `ps` para resolver tareas comunes de administración y diagnóstico de sistemas.

- **Ver todos los procesos del sistema (sintaxis estándar)**
- Este es uno de los comandos más utilizados. Muestra todos los procesos (`-e`) en formato completo (`-f`).
- **Ver todos los procesos del sistema (sintaxis BSD)**
- El equivalente en sintaxis BSD. Muestra todos los procesos (`a`), incluyendo los que no tienen terminal (`x`), en un formato orientado al usuario (`u`).
- **Imprimir un árbol de procesos (sintaxis UNIX)**
- Muestra todos los procesos (`-e`) en formato de trabajos (`j`) y los presenta en una jerarquía de árbol (`H`).
- **Imprimir un árbol de procesos (sintaxis BSD)**
- Una alternativa de estilo BSD que muestra todos los procesos (`ax`) en formato de trabajos (`j`) con un dibujo del árbol (`f`).
- **Obtener información sobre hilos**
- Muestra todos los procesos (`-e`) con sus hilos (`-L`) en formato completo (`-f`), añadiendo columnas como LWP y NLWP.
- **Ver todos los procesos ejecutados por el usuario** `**root**`
- Selecciona los procesos cuyo usuario real (`-U`) y efectivo (`-u`) es `root`, y los muestra en formato de usuario (`u`).
- **Crear un listado con formato personalizado**
- Un ejemplo avanzado de formato personalizado (`-eo`) que muestra una selección de columnas específicas, incluyendo el ID de hilo (tid), la clase de scheduling (class) y el ancho de la columna wchan fijado en 14 caracteres.
- **Imprimir solo el PID de** `**syslogd**`
- Selecciona el proceso por su nombre de comando (`-C syslogd`), formatea la salida para mostrar solo el PID (`-o pid`), y el signo igual (`=`) suprime la cabecera.
- **Imprimir solo el nombre del comando del PID 42**
- Utiliza el "modo rápido" (`-q`) para leer eficientemente solo la información del PID 42, saltándose otros filtros y ordenamientos. Luego muestra únicamente el nombre del comando (`-o comm=`), suprimiendo la cabecera.

### 8.0 Apéndices de Referencia Rápida

Esta sección final proporciona un conjunto de tablas de referencia para una consulta rápida durante el uso diario del comando `ps`.

#### 8.1 Códigos de Estado del Proceso (STAT)

La columna `STAT` o `S` muestra el estado actual de un proceso mediante un código de una o más letras.

|   |   |
|---|---|
|Código|Descripción|
|`**D**`|Sueño ininterrumpible (generalmente por E/S).|
|`**R**`|En ejecución o listo para ejecutar (en la cola de ejecución).|
|`**S**`|Sueño interrumpible (esperando que se complete un evento).|
|`**T**`|Detenido por una señal de control de trabajos.|
|`**t**`|Detenido por el depurador (_debugger_) durante el rastreo.|
|`**Z**`|Proceso difunto ("zombie"), terminado pero no eliminado por su padre.|
|`**I**`|Hilo del kernel en estado inactivo (_Idle_).|
|`**X**`|Muerto (nunca debería verse).|
|`**W**`|Paginando (no válido desde el kernel 2.6.xx).|

**Nota:** Con formatos de estilo BSD, pueden aparecer caracteres adicionales: `<`: alta prioridad; `N`: baja prioridad; `L`: páginas bloqueadas en memoria; `s`: líder de sesión; `l`: multi-hilo; `+`: en el grupo de procesos en primer plano.

#### 8.2 Especificadores de Formato Estándar (Selección)

Esta es una selección de los especificadores más útiles para usar con la opción `-o` (`--format`) y `--sort`. La lista completa es muy extensa.

|   |   |   |
|---|---|---|
|Código|Cabecera|Descripción|
|`pid`|`PID`|ID del Proceso.|
|`ppid`|`PPID`|ID del Proceso Padre.|
|`user`|`USER`|Nombre de usuario efectivo.|
|`ruser`|`RUSER`|Nombre de usuario real.|
|`group`|`GROUP`|Nombre del grupo efectivo.|
|`%cpu`|`%CPU`|Porcentaje de uso de CPU durante la vida del proceso.|
|`%mem`|`%MEM`|Porcentaje de memoria física (RSS) utilizada por el proceso.|
|`rss`|`RSS`|Tamaño del conjunto residente (memoria física no intercambiada), en KiB.|
|`vsz`|`VSZ`|Tamaño total de la memoria virtual del proceso, en KiB.|
|`stat`|`STAT`|Estado del proceso, en formato multi-carácter.|
|`comm`|`COMMAND`|Nombre del comando (solo el ejecutable).|
|`args`|`COMMAND`|Comando con todos sus argumentos.|
|`etime`|`ELAPSED`|Tiempo transcurrido desde que se inició el proceso (`[[DD-]hh:]mm:ss`).|
|`lstart`|`STARTED`|Fecha y hora de inicio del proceso.|
|`ni`|`NI`|Valor "nice" (prioridad de scheduling).|
|`pri`|`PRI`|Prioridad del proceso.|

#### 8.3 Variables de Entorno Relevantes

Ciertas variables de entorno pueden modificar el comportamiento por defecto de `ps`.

|   |   |
|---|---|
|Variable|Función|
|`PS_FORMAT`|Permite establecer un formato de salida por defecto, usando la misma sintaxis que la opción `-o`.|
|`COLUMNS`|Sobrescribe el ancho de pantalla detectado automáticamente.|
|`LINES`|Sobrescribe el alto de pantalla detectado automáticamente.|
|`PS_PERSONALITY`|Permite forzar a `ps` a emular el comportamiento de una implementación específica (p. ej., `bsd`, `linux`, `posix`).|

**Advertencia:** En general, es una mala idea configurar estas variables de forma permanente. La única excepción recomendada es `PS_PERSONALITY`. Para asegurar un comportamiento consistente y moderno, se aconseja establecer `PS_PERSONALITY=linux` en el entorno de su shell. Sin esta configuración, `ps` puede seguir "las partes inútiles y malas del estándar Unix98".