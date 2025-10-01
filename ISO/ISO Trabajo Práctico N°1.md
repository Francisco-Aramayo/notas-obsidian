
# 1. Características de GNU/Linux

## a.

GNU / Linux es software libre, permitiendo a cualquiera poder ejecutar estudiar, distribuir y modificar el código fuente del sistema operativo. También cuenta con una gran estabilidad y seguridad, lo cual lo vuelve excelente para servidores o entornos críticos.

Permite a los usuarios personalizar el sistema como ningún otro, pudiendo elegir entre distintos gestores de ventanas y distribuciones, logrando una flexibilidad única.

Además es una herramienta poderosa para desarrolladores, administradores de sistemas y usuarios avanzados, gracias a la línea de comandos, se pueden automatizar tareas y controlar el sistema con mucha eficiencia y precisión.

## b.

Hoy en día predomina en el mercado windows  y mac. Mac es el más similar por estar basado en UNIX, pero a nivel comercial es software propietario con código fuente cerrado. Esto significa que tienen mas restricciones de uso, costos de licencia, etc. 

## c.

GNU es un sistema operativo libre basado en unix que busca crear un ecosistema informático completamente libre, con las cualidades mencionadas antes.

Fue fundado por Richard Stallman en 1983, impulsado por un proyecto comunitario Free Software foundation. El proyecto desarrollo herramientas muy importantes como el compilador GCC, editor de texto Emacs, la shell bash y herramientas de la línea de comandos.

A GNU le faltaba el kernel, que no apareció hasta 1991 de la mano de Linus Torvalds, dando lugar a los sistemas operativos que hoy llamamos “linux”.

## d.

El proyecto GNU, iniciado por **Richard Stallman** en **1983**, es una iniciativa para crear un **sistema operativo completamente libre**.

Su principal objetivo es que el software sea accesible para todos, con la **libertad de usarlo, estudiarlo, modificarlo y compartirlo**.

A lo largo de los años, el proyecto desarrolló herramientas esenciales como el compilador **GCC** y la terminal **Bash**.

Cuando **Linus Torvalds** creó el núcleo **Linux** en 1991 y lo combinó con las herramientas de GNU, se formó el sistema que hoy conocemos como **GNU/Linux**.

## e.

La multitarea es la capacidad de un sistema operativo para ejecutar múltiples tareas o procesos de forma aparentemente simultánea. Existen dos tipos de multitarea:

- **Multitarea cooperativa**: Cada proceso debe ceder voluntariamente el control al sistema operativo para que otro proceso pueda ejecutarse. Si un programa se cuelga, puede bloquear todo el sistema. Este tipo de multitarea fue común en sistemas más antiguos como las primeras versiones de Windows y macOS.
- **Multitarea preferente (o con apropiación)**: El sistema operativo decide cuándo detener un proceso para ejecutar otro. Utiliza un **planificador de tareas** para asignar a cada proceso un "turno" de tiempo de CPU. Esto garantiza que ningún proceso pueda monopolizar el procesador, lo que aumenta la estabilidad y la capacidad de respuesta del sistema.

Linux hace uso extensivo de la multitarea preferente. Su kernel incluye un planificador de tareas sofisticado que distribuye el tiempo del CPU entre todos los procesos de manera equitativa y eficiente.

Es por eso que es tan estable, robusto y confiable para tantas aplicaciones.

## f.

POSIX (Portable Operating System Interface) es un conjunto de estándares de la IEE cuyo objetivo es garantizar que el software escrito para un sistema pueda compilarse y ejecutarse en otros sistemas compatibles sin necesidad de modificar el código fuente.

Esto determina la portabilidad, reduciendo el tiempo y el costo de desarrollo. Es utilizado en los sistemas tipo UNIX como Linux y macos.

Los componentes claves de estandarización de POSIX son:

- Llamadas al sistema
- Utilidades de línea de comandos
- Interfaz de shell

# 2. Distribuciones de GNU/Linux

## a.

Una distribución linux es un sistema operativo completo y listo para usar, construido sobre el núcleo y las herramientas GNU. Además viene con una interfaz gráfica (gestor de ventanas) y gestor de paquetes, que permite descargar una gran cantidad de software libre.

Se pueden mencionar las siguientes distribuciones:

- Debian
- Fedora
- Arch
- Ubuntu

Debian es un proyecto hecho por una comunidad, utiliza el gestor de paquetes APT. Ubuntu en cambio, se basa en Debian, usando los repositorios APT , desarrollado por Canonical (una empresa).

Fedora en cambio es la distribución de vanguardia de redhat. Tiene un gran interés en el software libre, utiliza el gestor de paquetes DNF y suele traer las últimas versiones del software disponible.

Arch es bastante flexible, permitiendo poder armar el sistema operativo con el gestor y interfaz gráfica que uno desee, así como que aplicaciones vienen por defecto (algo que varía mucho de distro en distro).

## b.

### Debian

- **Filosofía**: Enfoque en la **estabilidad, la libertad de software y la fiabilidad**. Sus paquetes se prueban exhaustivamente antes de ser incluidos en la versión "estable".
- **Gestor de paquetes**: Utiliza `APT` y paquetes `.deb`.
- **Ciclo de lanzamiento**: Sigue un modelo de "lanzamiento fijo", con versiones estables cada 2 años aproximadamente. Esta estabilidad la hace muy popular en **servidores**.
- **Público objetivo**: Usuarios que priorizan la estabilidad y el software libre. Es la base de muchas otras distros (incluyendo Ubuntu) y es la elección preferida para servidores y entornos críticos.

### Fedora

- **Filosofía**: Sirve como un "laboratorio" para **nuevas tecnologías**. Es el proyecto comunitario de Red Hat, por lo que las innovaciones que se prueban en Fedora a menudo llegan a la versión empresarial de Red Hat Enterprise Linux (RHEL).
- **Gestor de paquetes**: Utiliza `DNF` y paquetes `.rpm`.
- **Ciclo de lanzamiento**: Tiene un ciclo de lanzamiento más rápido, con una nueva versión cada 6 meses, lo que la convierte en una opción para desarrolladores y usuarios que quieren las **últimas versiones del software**.
- **Público objetivo**: Desarrolladores, entusiastas y usuarios que desean tener acceso a las tecnologías más recientes sin esperar.

### Arch Linux

- **Filosofía**: Se enfoca en la **simplicidad, el minimalismo y el control total del usuario**. El lema "hazlo tú mismo" (DIY) es central en su diseño. No viene con software preinstalado más allá de lo básico.
- **Gestor de paquetes**: Utiliza `Pacman`. Es conocida por su repositorio comunitario (AUR - Arch User Repository) que permite a los usuarios instalar software fácilmente.
- **Ciclo de lanzamiento**: Sigue un modelo **"Rolling Release"** (lanzamiento continuo). Esto significa que no hay versiones fijas; el sistema se actualiza constantemente a medida que los paquetes nuevos están disponibles, lo que te garantiza tener siempre el software más actual.
- **Público objetivo**: Usuarios avanzados, desarrolladores y personas que desean un control total sobre su sistema y no les molesta una curva de aprendizaje más alta.

### Ubuntu

- **Filosofía**: Busca la **facilidad de uso y la accesibilidad** para los usuarios de escritorio, sin sacrificar la estabilidad. Está respaldada por la empresa Canonical, que le da un enfoque más comercial.
- **Gestor de paquetes**: Basado en Debian, utiliza `APT` y paquetes `.deb`.
- **Ciclo de lanzamiento**: Ofrece versiones regulares cada 6 meses y versiones con **Soporte de Largo Plazo (LTS)** cada dos años, las cuales son muy populares por su estabilidad y por recibir actualizaciones de seguridad por varios años.
- **Público objetivo**: Es la opción más popular para **principiantes y usuarios de escritorio** en general, gracias a su facilidad de instalación, su interfaz pulida y una vasta comunidad de soporte. También es muy usada en servidores.

## c.

### Objetivos del Proyecto Debian

Los objetivos y la filosofía de Debian se describen en su [Contrato Social](https://www.google.com/search?q=https://www.debian.org/intro/social_contract.es.html) y en las [Directrices de Software Libre de Debian (DFSG)](https://www.google.com/search?q=https://www.debian.org/social_contract%23guidelines). Los principios clave son:

- **Crear un sistema operativo 100% libre**: Debian está comprometido a mantener su software completamente libre y de código abierto.
- **Ser una distribución de alta calidad**: El proyecto se esfuerza por desarrollar un sistema operativo fiable y estable, con un riguroso proceso de pruebas para garantizar la calidad.
- **Ser un proyecto no comercial**: Debian no es mantenido por una sola empresa, sino por una comunidad de voluntarios. Su desarrollo está abierto a la contribución de cualquier persona.
- **Estar al servicio de la comunidad**: El proyecto se organiza para servir a la comunidad del software libre y a sus usuarios, proporcionando un sistema operativo robusto y con soporte para múltiples arquitecturas.

### Breve cronología de Debian

- **1993**: El proyecto Debian es fundado por **Ian Murdock** el 16 de agosto con el objetivo de crear una distribución de Linux desarrollada abiertamente, en el espíritu de Linux y GNU. El nombre Debian proviene de la combinación de su nombre y el de su entonces novia, Debra.
- **1996**: **Bruce Perens** se convierte en el segundo líder del proyecto.
- **1997**: Se lanza **Debian 1.3 (Bo)** con 974 paquetes y cerca de 200 desarrolladores.
- **1998**: Se lanza **Debian 2.0 (Hamm)**, la primera versión basada en la biblioteca `glibc`, lo que permite un mayor número de paquetes.
- **A lo largo del tiempo**: Debian se convierte en la base de numerosas distribuciones (como Ubuntu, Kali Linux y Linux Mint) y es conocida por su estabilidad, lo que la hace muy popular para servidores y sistemas de misión crítica.

# 3. Estructura de GNU/Linux

## a.

- Kernel
- Herramientas del sistema GNU
- Software de usuario (aplicaciones y entorno)

## b.

### 1. El Núcleo (Kernel)

El **núcleo** (Linux) es la capa más baja y el corazón del sistema operativo. Es la única parte que interactúa directamente con el hardware de la computadora. Su función principal es gestionar los recursos del sistema, como:

- **Gestión de la memoria**: Asigna y protege la memoria para que los programas puedan ejecutarse sin interferir entre sí.
- **Gestión de procesos**: Controla la ejecución de los programas, asignándoles tiempo de CPU.
- **Controladores de dispositivos**: Permite que el sistema operativo se comunique con el hardware conectado (disco duro, tarjeta de red, teclado, etc.).

### 2. El Shell

El **shell** actúa como una interfaz entre el usuario y el núcleo. Es una capa de software que permite a los usuarios introducir comandos y ejecutar programas. La shell más común en GNU/Linux es **Bash** (Bourne Again Shell). A través del shell, el usuario puede:

- Ejecutar comandos como `ls`, `cd`, o `cp`.
- Automatizar tareas mediante scripts.

### 3. Las Utilidades y Aplicaciones

Esta es la capa más alta y visible para el usuario. Incluye todas las herramientas, programas y aplicaciones que se ejecutan sobre el núcleo y la shell. Esta capa se puede subdividir en:

- **Utilidades del sistema**: Herramientas básicas para la administración del sistema y la manipulación de archivos. Muchas de estas utilidades son parte del proyecto **GNU** (como `ls`, `mv`, `grep`, etc.).
- **Entornos de escritorio**: La interfaz gráfica de usuario (GUI) que permite interactuar con el sistema de forma visual, con ventanas, iconos y menús. Ejemplos populares son **GNOME**, **KDE** y **XFCE**.
- **Aplicaciones**: El software que los usuarios usan para tareas específicas, como navegadores web (Firefox), suites de oficina (LibreOffice) o reproductores multimedia.

# 4. Kernel

## a.

### 1. Gestión de Procesos

El kernel es responsable de crear, ejecutar, programar y finalizar los procesos (programas en ejecución). Decide qué proceso obtiene tiempo de CPU y por cuánto tiempo, gestionando la multitarea de manera eficiente.

### 2. Gestión de Memoria

Controla el uso de la memoria del sistema. El kernel asigna la memoria a los procesos, protege la memoria de un proceso para que no sea accedida por otro, y maneja el intercambio de datos entre la memoria RAM y el disco duro (memoria virtual).

### 3. Gestión de Archivos

Se encarga del sistema de archivos, lo que le permite crear, leer, escribir y eliminar archivos en el disco duro. El kernel traduce las solicitudes de software en operaciones reales de lectura y escritura en los dispositivos de almacenamiento.

### 4. Gestión de Dispositivos

El kernel gestiona los controladores de dispositivos. Permite que el sistema operativo se comunique con el hardware conectado, como el teclado, el mouse, la impresora, la tarjeta de red, la cámara web y las unidades de almacenamiento. Sin el kernel, los programas no podrían interactuar con estos dispositivos.

## b.

La versión **más reciente del kernel Linux** fue la **6.16**, lanzada oficialmente el **27 de julio de 2025.**

Hasta antes de la serie 2.6 (incluyendo la versión 2.4), el kernel Linux seguía un sistema de versionado bastante conocido:

- Usaba el **número de versión menor (b)** como indicador de la estabilidad:
    - **Par (even)** → versiones **estables** (release).
    - **Impar (odd)** → versiones **en desarrollo** (development).
- Ejemplos conocidos:
    - `2.3.x` era rama de desarrollo.
    - `2.4.x` era la rama estable que resultó de esa línea.

Este esquema claramente separaba dos ciclos: desarrollo por un lado, estabilidad por otro.

A partir de la versión **2.6**, se produjo un cambio sustancial en la estrategia de versionado y en el modelo de desarrollo:

1. **Eliminación del esquema par/impar**: la distinción entre versiones estables y de desarrollo dejó de hacerse mediante par/impar. Se abandonó esa estructura.
2. **Adopción de un solo ciclo de desarrollo continuo**:
    - No hay ramas separadas para desarrollo y estable; todo el trabajo se integra (“merge window”) y, al cabo de unas semanas (usualmente cada 9–10 semanas), se publica una nueva versión principal.
    - Las correcciones se aplican después mediante versiones “stable” (parches) mantenidas por responsables designados [kernel.org](https://www.kernel.org/releases.html?utm_source=chatgpt.com).
3. **Simplificación del esquema de numeración a partir de 3.x**:
    - Justo después de `2.6.39`, se pasó a la **versión 3.0**, sin cambios mayores en el modelo de desarrollo, simplemente se redujo la longitud de la numeración.
4. **Modelo actual (3.x, 4.x, 5.x, 6.x...)**:
    - **número principal (major)**: aumenta secuencialmente cuando Torvalds así lo decide.
    - **número menor (minor)**: representa la nueva versión.
    - **número de parche (patch)**: para pequeñas correcciones dentro de esa rama.
    - Ejemplo: una rama `6.15.x` corresponde a la versión menor `15` dentro de la serie mayor `6`.

Resumiendo, el criterio actual es más fluido, ágil, con ciclos de lanzamiento regulares y sin ramas de desarrollo paralelas.

## c.

Los archivos más importantes del kernel están ubicados principalmente en:

- **`/boot`**: Este directorio contiene los archivos necesarios para el proceso de arranque, incluyendo la imagen del kernel (`vmlinuz`), los archivos `initrd` (usados para cargar módulos y controladores iniciales) y los archivos de configuración del gestor de arranque (como GRUB).
- **`/lib/modules`**: En este directorio se almacenan los módulos del kernel. Estos módulos son partes del código del kernel que se pueden cargar y descargar dinámicamente. Cada versión del kernel instalada tiene su propio subdirectorio dentro de `/lib/modules`.

En resumen, mientras que la imagen principal del kernel está en el directorio `/boot`, los módulos que lo complementan se encuentran en `/lib/modules`. Esto permite que el gestor de arranque encuentre y cargue el kernel correcto para iniciar el sistema.

# 5. Intérprete de comandos(Shell)

## a.

El **shell** es un programa de interfaz de línea de comandos que actúa como intermediario entre el usuario y el núcleo (kernel) del sistema operativo. Su nombre, que en inglés significa "caparazón" o "concha", es una metáfora de su función: envuelve al núcleo y proporciona un entorno para que los usuarios se comuniquen con el sistema.

## b.

El shell te permite ejecutar comandos, programas y scripts para interactuar directamente con el sistema operativo. En lugar de usar una interfaz gráfica con clics, usas texto para escribir comandos como:

- **`ls`**: Para listar los archivos en un directorio.
- **`cp`**: Para copiar archivos.
- **`mkdir`**: Para crear un nuevo directorio.

## c.

Existen varios shells, cada uno con sus propias características, pero todos cumplen la misma función principal. El más popular en los sistemas GNU/Linux es **Bash** (Bourne Again Shell). Otros shells comunes incluyen Zsh, Fish y KornShell.

### 🔹 **Bash (Bourne Again Shell)**

- La más común en GNU/Linux (default en la mayoría de distros).
- Compatible con la vieja **sh**.
- Buen balance entre simplicidad y potencia.
- Gran cantidad de documentación y soporte.

### 🔹 **Zsh (Z Shell)**

- Similar a bash pero más personalizable.
- Autocompletado avanzado y sugerencias.
- Soporta *plugins* y *themes* (ej: **oh-my-zsh**).
- Popular entre desarrolladores que buscan comodidad.

### 🔹 **Fish (Friendly Interactive Shell)**

- Muy fácil de usar desde cero.
- Autocompletado inteligente y resaltado de sintaxis integrado.
- Configuración simple (no requiere muchos scripts ni plugins).
- No es 100% compatible con bash (scripts pueden fallar).

### 🔹 **Korn Shell (ksh)**

- Más antigua (años 80), muy usada en Unix clásico.
- Combina características de **sh** y **csh**.
- Estable y eficiente en entornos empresariales.
- Hoy menos popular en Linux frente a bash/zsh.

---

👉 **En resumen**:

- **Bash** → estándar y ampliamente usado.
- **Zsh** → más personalizable y moderno.
- **Fish** → fácil, intuitivo, pero menos compatible.
- **Ksh** → clásico, estable, más presente en Unix que en Linux.

## d.

- **Comandos internos (built-in)**:
    - Están integrados dentro de la propia shell (ej. `cd`, `echo`, `exit`).
    - No tienen un ejecutable en disco, se ejecutan directamente desde la shell.
- **Comandos externos**:
    - Son programas almacenados en el sistema de archivos.
    - Usualmente se encuentran en directorios que están en el **`$PATH`**, como:
        - `/bin`
        - `/usr/bin`
        - `/sbin`
        - `/usr/sbin`
        - `/usr/local/bin`

## e.

- El **kernel** es el núcleo: gestiona hardware, memoria, procesos, dispositivos.
- La **shell** es un programa de usuario que **interactúa con el kernel** a través de llamadas al sistema.
- No está dentro del kernel porque:
    - Se puede reemplazar por otra (bash, zsh, fish, etc.).
    - No cumple funciones de gestión del hardware, solo interpreta comandos.
    - Mantenerlas separadas da modularidad y flexibilidad al sistema.

## f.

sí, cada usuario puede tener una shell diferente.

- **Dónde se define**:
    - En el archivo `/etc/passwd`, en el último campo de cada línea (ejemplo: `/bin/bash`, `/usr/bin/zsh`).
    - También con el comando `chsh` (*change shell*).
- **Quién puede cambiarlo**:
    - **Usuario normal**: puede cambiar **su propia shell** (si está listada en `/etc/shells`).
    - **Administrador (root)**: puede cambiar la shell de cualquier usuario.

# 6.  El sistema de Archivos (File System) en Linux

## a.

Es la forma en que GNU/Linux **organiza y gestiona la información en discos y dispositivos de almacenamiento**.

Define:

- Cómo se guardan los datos.
- Cómo se nombran los archivos y directorios.
- Cómo se accede a ellos y qué permisos tienen.

En Linux todo se representa como un archivo (inclusive dispositivos, procesos, sockets, etc.).

## b.

Linux usa una estructura jerárquica en forma de **árbol**, con un único punto de inicio: `/` (root).

Los directorios más importantes según el **FHS (Filesystem Hierarchy Standard)** son:

- `/` → raíz del sistema, desde donde cuelga todo.
- `/bin` → binarios esenciales (ejecutables de usuario como `ls`, `cp`).
- `/sbin` → binarios esenciales de administración (ej. `fdisk`, `mount`).
- `/boot` → archivos de arranque (kernel, GRUB).
- `/dev` → archivos de dispositivos (discos, terminales, USB, etc.).
- `/etc` → archivos de configuración del sistema.
- `/home` → directorios personales de los usuarios.
- `/lib`, `/lib64` → bibliotecas compartidas necesarias para ejecutar binarios.
- `/media` → punto de montaje para medios extraíbles (USB, DVD).
- `/mnt` → punto de montaje temporal.
- `/opt` → aplicaciones adicionales instaladas por terceros.
- `/proc` → información del kernel y procesos (sistema de archivos virtual).
- `/root` → directorio personal del usuario root.
- `/tmp` → archivos temporales.
- `/usr` → programas y archivos no esenciales para el arranque (ej. `/usr/bin`, `/usr/share`).
- `/var` → archivos variables (logs, spool de correo, colas de impresión).

📌 **FHS**: *Filesystem Hierarchy Standard*, el estándar que define cómo deben organizarse los directorios en sistemas tipo Unix (Linux, BSD).

## c.

Linux soporta muchos sistemas de archivos, entre ellos:

- **Nativos de Linux**:
    - `ext2`, `ext3`, `ext4` (más usados históricamente).
    - `XFS` (muy eficiente en archivos grandes).
    - `Btrfs` (moderno, con snapshots y compresión).
    - `ReiserFS` (menos usado hoy).
    - `F2FS` (optimizado para memorias flash/SSD).
- **De otros sistemas operativos**:
    - `FAT12/16/32` (Windows, BIOS, dispositivos USB).
    - `exFAT` (pendrives grandes, SDXC).
    - `NTFS` (Windows).
    - `HFS/HFS+` (macOS).
    - `ISO9660` (CD/DVD).

## d.

Sí, Linux puede montar y acceder a particiones de Windows:

- **FAT (12/16/32)**: soporte nativo desde hace muchos años.
- **NTFS**: acceso mediante el módulo **ntfs-3g**, que permite lectura y escritura.

Ejemplo:

```bash
sudo mount -t ntfs-3g /dev/sda1 /mnt/windows

```

# 7.  Particiones

### a. Definición. Tipos de particiones. Ventajas y desventajas

**Definición:**

Una **partición** es una división lógica dentro de un disco duro físico que permite organizar, gestionar y utilizar el espacio de almacenamiento como si fueran discos independientes.

**Tipos de particiones:**

1. **Primarias**
    - Máximo de 4 por disco (en esquema MBR).
    - Una de ellas puede ser **partición activa** (donde se instala el SO).
    - Se identifican directamente por la tabla de particiones.
2. **Extendida**
    - Sirve como "contenedor" para crear particiones lógicas.
    - Solo puede haber una extendida por disco.
3. **Lógicas**
    - Existen dentro de la partición extendida.
    - Permiten superar el límite de 4 particiones en MBR.
4. **GPT (GUID Partition Table)** – reemplazo moderno de MBR
    - Soporta hasta 128 particiones sin necesidad de extendidas ni lógicas.
    - Compatible con discos grandes (>2 TB).

**Ventajas y desventajas:**

- **Primarias:** rápidas y simples, pero limitadas en cantidad (4 en MBR).
- **Extendida/lógicas:** permiten más flexibilidad, pero añaden complejidad.
- **GPT:** sin límites prácticos y más confiable, pero no soportado por sistemas muy antiguos.

---

### b. Identificación de particiones en GNU/Linux

En Linux, los discos y particiones se identifican en **/dev/**.

- **IDE (antiguos, hasta ~2005):** `/dev/hd[a-d]` (ej: `/dev/hda1`, `/dev/hdb2`).
- **SCSI y SATA (actuales):** `/dev/sd[a-z]` (ej: `/dev/sda1`, `/dev/sdb3`).
- **NVMe (SSD modernos):** `/dev/nvme0n1pX` (ej: `/dev/nvme0n1p1`).

Convención:

- La letra identifica el disco (`sda` = primer disco SATA/SCSI, `sdb` = segundo).
- El número identifica la partición (`sda1` = primera partición del primer disco).

---

### c. Particiones mínimas para instalar GNU/Linux

Mínimo se necesitan **2 particiones**:

1. **Root (`/`)**
    - Tipo: primaria o lógica
    - Identificación: `/dev/sda1` (ejemplo)
    - File System: ext4 (típico)
    - Punto de montaje: `/`
2. **Swap** (intercambio, memoria virtual)
    - Tipo: primaria o lógica
    - Identificación: `/dev/sda2`
    - File System: área de intercambio
    - Punto de montaje: ninguno (es swap, no se monta como carpeta).

Opcionales pero recomendables:

- `/home` (para archivos de usuario).
- `/boot` (para el gestor de arranque, útil en configuraciones especiales).

---

### d. Ejemplos de particionamiento según la tarea

1. **Uso básico (PC personal):**
    - `/` → 30 GB, ext4
    - `swap` → 2 a 4 GB (dependiendo de la RAM)
    - `/home` → resto del disco, ext4
2. **Servidor web:**
    - `/` → 20 GB
    - `swap` → 4 GB
    - `/home` → 20 GB (usuarios)
    - `/var` → resto del disco (almacena logs, páginas web, bases de datos)
3. **Estación de trabajo (edición multimedia, desarrollo):**
    - `/` → 40 GB
    - `swap` → igual a RAM (si se usa hibernación)
    - `/home` → grande (archivos de usuario)
    - `/opt` → para software extra
4. **Sistema dual boot (Windows + Linux):**
    - `NTFS` → Windows
    - `/` → Linux root
    - `swap`
    - `/home` o partición compartida en NTFS/FAT32 para intercambio de archivos.

---

### e. Software para particionar

**1. Herramientas gráficas:**

- **GParted** (GNU/Linux)
    - Muy popular, entorno gráfico amigable.
    - Soporta ext, NTFS, FAT, etc.
- **KDE Partition Manager**
    - Similar a GParted pero para entorno KDE.

**2. Herramientas en consola (GNU/Linux):**

- **fdisk** (para MBR)
- **gdisk** (para GPT)
- **parted** (para ambos esquemas, más moderno).

**3. Herramientas de Windows (comparación):**

- **Disk Management (Administrador de discos)**
    - Integrado, limitado en formatos.
- **EaseUS Partition Master**, **AOMEI Partition Assistant**
    - Comerciales, fáciles de usar, pero no tan flexibles con ext4.

**Comparación:**

- Linux (fdisk/parted/GParted) → más potentes y flexibles.
- Windows (nativos) → fáciles pero limitados.
- Software de terceros (EaseUS, AOMEI) → más amigables, pero algunos pagos.

# 8. Arranque de un sistema op

### a. ¿Qué es el BIOS? ¿Qué tarea realiza?

- **BIOS (Basic Input/Output System):** firmware almacenado en un chip de la placa madre.
- **Funciones principales:**
    - Inicializar y comprobar el hardware al encender (POST: *Power-On Self Test*).
    - Ofrecer una interfaz básica entre hardware y software.
    - Localizar un dispositivo de arranque (disco, USB, red) y cargar el gestor de arranque.

---

### b. ¿Qué es UEFI? ¿Cuál es su función?

- **UEFI (Unified Extensible Firmware Interface):** sucesor moderno del BIOS.
- **Funciones:**
    - Inicializa el hardware y carga el sistema operativo.
    - Soporta discos grandes (>2 TB) gracias al uso de GPT.
    - Interfaz gráfica, soporte de mouse, configuraciones más avanzadas.
    - Incluye seguridad como **Secure Boot**.

---

### c. ¿Qué es el MBR? ¿Qué es el MBC?

- **MBR (Master Boot Record):**
    - Primer sector (512 bytes) de un disco (en sistemas BIOS).
    - Contiene:
        1. Código de arranque.
        2. Tabla de particiones (máx. 4 primarias).
        3. Firma de arranque (0x55AA).
- **MBC:** no es un término estándar en este contexto, probablemente tu apunte/profesor se refiera a **Master Boot Code** (la parte del MBR que contiene el código de arranque), diferenciándolo de la tabla de particiones.

---

### d. ¿A qué hacen referencia las siglas GPT? ¿Qué sustituye? Indique cuál es su formato.

- **GPT (GUID Partition Table):**
    - Nuevo esquema de particionado que reemplaza al MBR.
    - Usa identificadores únicos globales (GUID).
    - Permite hasta 128 particiones (sin necesidad de extendidas/lógicas).
    - Compatible con discos de más de 2 TB.
- **Formato:** estructura con cabecera GPT y tabla redundante (copias de seguridad) para mayor seguridad ante corrupción.

---

### e. ¿Cuál es la funcionalidad de un Gestor de Arranque?

- **Función:** programa que carga el sistema operativo en memoria después de BIOS/UEFI.
- **Tipos:**
    - **De una sola etapa:** muy simples, cargan directamente el SO (ej: MBR clásico).
    - **De varias etapas:** más complejos, permiten elegir entre varios sistemas (dual boot).
- **Ubicación:**
    - En el MBR (en sistemas BIOS).
    - En la partición EFI (en sistemas UEFI).
- **Ejemplos conocidos:**
    - **GRUB (GNU GRUB):** muy usado en GNU/Linux.
    - **LILO (Linux Loader):** antiguo, hoy en desuso.
    - **Syslinux/Isolinux.**
    - **Windows Boot Manager.**

---

### f. Pasos del proceso de *bootstrap* (desde que se enciende la PC hasta que el SO se carga)

1. **Encendido:** la fuente entrega energía.
2. **Firmware (BIOS/UEFI):** inicializa hardware, hace POST.
3. **Selección de dispositivo de arranque:** disco, USB, red.
4. **Carga del gestor de arranque:** desde el MBR o partición EFI.
5. **Gestor de arranque:** presenta menú, selecciona y carga kernel del SO.
6. **Kernel del SO:** se carga en memoria y comienza a ejecutarse.
7. **Inicialización de procesos del sistema:** se carga el proceso inicial (`init` o `systemd` en Linux).

---

### g. Proceso de arranque en GNU/Linux (principales pasos)

1. **BIOS/UEFI:** inicialización y búsqueda de dispositivo de arranque.
2. **Gestor de arranque (ej: GRUB):** carga el kernel de Linux y el initramfs (disco RAM inicial).
3. **Kernel:**
    - Detecta hardware.
    - Monta el sistema de archivos raíz (root).
    - Inicia el proceso `init` (o `systemd`).
4. **Init/systemd:**
    - Monta otros sistemas de archivos.
    - Inicia servicios del sistema (red, login, demonios).
5. **Login:** se inicia el entorno gráfico o consola de inicio de sesión.

---

### h. Proceso de parada (shutdown) en GNU/Linux

1. **Invocación del apagado:** con `shutdown`, `poweroff`, `halt` o desde interfaz gráfica.
2. **systemd/init:** envía señal para terminar procesos.
3. **Sincronización:** se vacían buffers y se escriben datos pendientes en disco.
4. **Desmontaje:** sistemas de archivos se desmontan de forma segura.
5. **Apagado del hardware:** el firmware corta la alimentación de la máquina.

---

### i. ¿Es posible tener en una PC GNU/Linux y otro SO instalado? Justifique.

- **Sí, es posible (dual boot o multi-boot).**
- Los sistemas pueden convivir en el mismo disco duro siempre que tengan **particiones separadas**.
- El gestor de arranque (ej: GRUB) permite elegir qué sistema iniciar al encender la computadora.
- Ejemplo típico: Windows en NTFS + Linux en ext4 + partición swap.

# 9. Archivos y editores

---

## 9. Archivos y editores

### a. ¿Cómo se identifican los archivos en GNU/Linux?

- En GNU/Linux los **archivos se identifican por su nombre**, no por la extensión (aunque se usen extensiones por convención).
- Ejemplo: `documento.txt`, `script.sh`, `prueba.exe` → el sistema no usa la extensión para saber el tipo, sino el **contenido** y los **permisos**.
- Lo que define el uso de un archivo es:
    - **Permisos** (ejecutable, lectura, escritura).
    - **Comando `file`**, que detecta el tipo real de archivo.

---

### b. Editores de texto y comandos de visualización

**Editores:**

1. **vim (Vi IMproved):**
    - Editor muy potente, modo consola.
    - Tiene modos: *comando*, *inserción* y *línea de órdenes*.
    - Ideal para administradores de sistemas.
    - Ejemplo:
        - `i` → insertar texto.
        - `:wq` → guardar y salir.
        - `:q!` → salir sin guardar.
2. **nano:**
    - Editor simple, fácil de usar.
    - Muestra atajos en pantalla (Ctrl+O guardar, Ctrl+X salir).
3. **mcedit:**
    - Editor de texto que viene con **Midnight Commander (mc)**.
    - Amigable, menú con atajos, más parecido a un editor gráfico.

**Comandos de visualización:**

- **cat archivo:** muestra el contenido completo del archivo en la terminal.
- **more archivo:** muestra el contenido página por página. Navegación básica con `Espacio` (avanza) y `q` (salir).
- **less archivo:** similar a `more` pero más avanzado. Permite moverse hacia adelante y atrás con teclas de flecha, `PgUp`, `PgDn`.

---

### c. Crear archivo “prueba.exe” con vim

Pasos:

```bash
cd ~              # Ir al directorio personal
vim prueba.exe    # Abrir el editor vim

```

Dentro de vim:

- Presionar `i` para entrar en **modo inserción**.
- Escribir:
    
    ```
    12345678 - Juan Pérez
    
    ```
    
    (reemplazás con tu número de alumno y tu nombre).
    
- Presionar `Esc`.
- Escribir `:wq` y Enter → guardar y salir.

Ahora en tu home tendrás el archivo `prueba.exe`.

---

### d. Comando **file**

- Sirve para identificar el **tipo real de archivo** por su contenido (no por la extensión).
    
    Ejemplos:
    

```bash
file prueba.exe
file /bin/ls
file foto.jpg

```

Resultados típicos:

- `prueba.exe: ASCII text` (aunque tenga `.exe`, en Linux se ve como texto).
- `/bin/ls: ELF 64-bit LSB executable` (ejecutable binario Linux).
- `foto.jpg: JPEG image data`.

👉 Diferencia: el comando **no se basa en el nombre**, sino en el **contenido binario del archivo**.

---

### e. Comandos de manejo de archivos

1. **cd (change directory):** cambia de directorio.
    - `cd /home/usuario`
    - `cd ..` (subir un nivel).
2. **mkdir (make directory):** crea directorios.
    - `mkdir proyectos`
    - `mkdir -p dir1/dir2/dir3` (crea árbol de directorios).
3. **rmdir (remove directory):** elimina directorios vacíos.
    - `rmdir proyectos`
4. **ln (link):** crea enlaces.
    - **Duros (hard links):** apuntan al mismo inodo.
        - `ln archivo enlace1`
    - **Simbólicos (soft links, como accesos directos):**
        - `ln -s archivo enlace2`
5. **tail:** muestra las últimas líneas de un archivo.
    - `tail archivo` (últimas 10 líneas).
    - `tail -n 20 archivo` (últimas 20).
    - `tail -f archivo` (seguimiento en vivo, útil para logs).
6. **locate:** busca archivos en el sistema usando una base de datos.
    - `locate documento.txt`
    - (Necesita que la base esté actualizada con `updatedb`).
7. **ls (list):** lista el contenido de un directorio.
    - `ls`
    - `ls -l` (detalles).
    - `ls -a` (incluye ocultos).
8. **pwd (print working directory):** muestra la ruta actual.
    - `pwd`
9. **cp (copy):** copia archivos/directorios.
    - `cp archivo.txt copia.txt`
    - `cp -r dir1 dir2` (copia recursiva de directorios).
10. **mv (move):** mueve o renombra archivos.
    - `mv archivo.txt /home/usuario/`
    - `mv viejo.txt nuevo.txt`
11. **find:** busca archivos recorriendo directorios.
    - `find /home -name "*.txt"` (buscar todos los `.txt`).
    - `find / -type d -name "backup"` (buscar directorios llamados backup).

---

# 11.

### **man (manual)**

- **Funcionamiento:** Muestra la página de manual (documentación) de un comando. Es la principal herramienta para obtener ayuda sobre comandos, programas, llamadas al sistema y otros archivos en Linux. Las páginas de `man` están organizadas por secciones.
- **Parámetros:** El uso más común es `man <comando>`. Puedes especificar una sección con `man <sección> <comando>` (ej. `man 2 intro` para ver la introducción a las llamadas al sistema). Otras opciones incluyen `k` para buscar en las descripciones de las páginas de manual (`man -k <palabra_clave>`).
- **Ubicación:** Generalmente se encuentra en `/usr/bin/man`.

### **shutdown**

- **Funcionamiento:** Apaga, reinicia o detiene el sistema de forma segura. Notifica a todos los usuarios conectados y detiene los procesos en ejecución antes de apagar, evitando la corrupción de datos.
- **Parámetros:**
    - `shutdown now`: Apaga el sistema inmediatamente.
    - `shutdown -r now`: Reinicia el sistema inmediatamente.
    - `shutdown +<minutos> "mensaje"`: Programa un apagado en `x` minutos con un mensaje de aviso para los usuarios.
    - `shutdown -c`: Cancela un apagado programado.
- **Ubicación:** Generalmente en `/sbin/shutdown`. Requiere privilegios de superusuario (`sudo`).

### **reboot**

- **Funcionamiento:** Reinicia el sistema. Es un atajo para `shutdown -r now`.
- **Parámetros:**
    - `reboot`: Reinicia el sistema inmediatamente.
    - `reboot -f`: Fuerza un reinicio sin pasar por el proceso normal de apagado (evitando que los procesos se cierren de forma segura).
- **Ubicación:** Generalmente en `/sbin/reboot` o es un alias para `shutdown`. Requiere privilegios de superusuario (`sudo`).

### **halt**

- **Funcionamiento:** Detiene el sistema y lo deja en un estado en el que ya no está funcionando, pero el hardware sigue encendido. Es un atajo para `shutdown -H now`.
- **Parámetros:**
    - `halt`: Detiene el sistema.
    - `halt -p` o `poweroff`: Apaga completamente el sistema y desconecta la energía.
- **Ubicación:** Generalmente en `/sbin/halt` o es un alias para `shutdown`. Requiere privilegios de superusuario (`sudo`).

### **uname**

- **Funcionamiento:** Muestra información detallada sobre el sistema, como el nombre del kernel, el nombre del host y la arquitectura del hardware.
- **Parámetros:**
    - `uname -s`: Muestra el nombre del kernel (por defecto).
    - `uname -n`: Muestra el nombre del host.
    - `uname -r`: Muestra la versión del kernel.
    - `uname -a`: Muestra toda la información. Es el parámetro más común.
- **Ubicación:** Generalmente en `/bin/uname`.

### **dmesg**

- **Funcionamiento:** Muestra el "buffer" de mensajes del kernel. Es una herramienta esencial para la **resolución de problemas de hardware** y el diagnóstico del sistema, ya que muestra mensajes del kernel sobre dispositivos detectados, controladores, errores y eventos del sistema durante el arranque.
- **Parámetros:**
    - `dmesg`: Muestra todo el buffer de mensajes.
    - `dmesg | less`: Permite paginar la salida para leerla más fácilmente.
    - `dmesg -T`: Muestra la salida con marcas de tiempo legibles para el usuario.
- **Ubicación:** Generalmente en `/bin/dmesg`.

### **lspci**

- **Funcionamiento:** Muestra información sobre todos los dispositivos y buses PCI. Es útil para identificar el hardware de la placa madre, como tarjetas gráficas, tarjetas de red, controladores USB, etc.
- **Parámetros:**
    - `lspci`: Muestra un resumen de los dispositivos.
    - `lspci -v`: Muestra una salida más detallada.
    - `lspci -vv`: Muestra una salida aún más detallada, incluyendo configuraciones específicas.
- **Ubicación:** Generalmente en `/usr/bin/lspci`.

### **at**

- **Funcionamiento:** Programa la ejecución de un comando en una fecha y hora específicas en el futuro. Es útil para tareas únicas, a diferencia de `cron` que es para tareas recurrentes.
- **Parámetros:**
    - `at <hora> <fecha>`: Inicia un "prompt" para ingresar el comando a ejecutar.
    - `at now + 5 minutes`: Programa un comando para que se ejecute en 5 minutos.
    - `atq`: Muestra la lista de trabajos en la cola de `at`.
    - `atrm <ID_trabajo>`: Elimina un trabajo de la cola.
- **Ubicación:** Generalmente en `/usr/bin/at`. El servicio `atd` debe estar en ejecución para que funcione.

### **netstat**

- **Funcionamiento:** Muestra las conexiones de red activas (entrantes y salientes), las tablas de enrutamiento, las estadísticas de las interfaces y la información de los "sockets" de red. Es una herramienta clave para la **solución de problemas de red**.
- **Parámetros:**
    - `netstat -tulnp`: Muestra una lista de todos los sockets TCP y UDP que están escuchando, con sus respectivos números de puerto, el programa que los usa y el ID del proceso.
    - `netstat -r`: Muestra la tabla de enrutamiento del kernel.
- **Ubicación:** Generalmente en `/bin/netstat` o `/usr/bin/netstat`. En sistemas modernos, se ha reemplazado por el comando `ss`.

### **head**

- **Funcionamiento:** Muestra las primeras líneas de un archivo de texto. Es muy útil para examinar rápidamente el comienzo de archivos grandes, como logs o archivos de configuración.
- **Parámetros:**
    - `head <archivo>`: Muestra las primeras 10 líneas (por defecto).
    - `head -n <número> <archivo>`: Muestra el número de líneas especificado (ej. `head -n 5 /var/log/syslog`).
- **Ubicación:** Generalmente en `/usr/bin/head`.

### **tail**

- **Funcionamiento:** Muestra las últimas líneas de un archivo de texto. Es particularmente útil para **monitorear archivos de registro** en tiempo real.
- **Parámetros:**
    - `tail <archivo>`: Muestra las últimas 10 líneas (por defecto).
    - `tail -n <número> <archivo>`: Muestra el número de líneas especificado (ej. `tail -n 20 /var/log/syslog`).
    - `tail -f <archivo>`: Muestra las últimas líneas y luego "sigue" el archivo, mostrando las nuevas líneas a medida que se agregan. Esta es una función muy utilizada para el monitoreo en vivo de logs.
- **Ubicación:** Generalmente en `/usr/bin/tail`.

---

# 12. Procesos

### a. ¿Qué es un proceso?

Un **proceso** es una instancia de un programa en ejecución. Es una entidad activa que incluye el código del programa, sus datos, su estado de ejecución y recursos asociados como la memoria, los archivos abiertos y las señales. El sistema operativo gestiona y programa estos procesos para que compartan el tiempo de la CPU.

- **PID (Process IDentifier):** Es un número único asignado por el kernel a cada proceso al ser creado. Sirve para identificar y manipular un proceso de manera individual, por ejemplo, para enviarle una señal o para terminarlo.
- **PPID (Parent Process IDentifier):** Es el PID del proceso padre, es decir, el proceso que lo creó. Cada proceso, excepto el proceso **init** (o `systemd` en sistemas modernos), es creado por otro proceso, estableciendo una jerarquía de procesos.
- **¿Todos los procesos tienen estos atributos?** Sí, todos los procesos en GNU/Linux tienen un PID y un PPID. El proceso `init` (con PID 1) es la excepción, ya que no tiene un padre y su PPID es 0. Todos los demás procesos son descendientes de `init`.

**Otros atributos de un proceso:**

- **UID/EUID (User ID/Effective User ID):** Identifica al usuario propietario del proceso.
- **GID/EGID (Group ID/Effective Group ID):** Identifica al grupo propietario del proceso.
- **Estado:** Indica el estado actual del proceso (por ejemplo, en ejecución, detenido, dormido, zombie).
- **Prioridad:** Determina la preferencia de programación del proceso por el kernel.
- **CPU y uso de memoria:** La cantidad de recursos que el proceso está consumiendo.

---

### b. Comandos de gestión de procesos

A continuación se detalla el funcionamiento, parámetros y ubicación de los comandos solicitados. Si un comando no está disponible, se puede instalar con el gestor de paquetes de la distribución (por ejemplo, `apt install` en Debian/Ubuntu, `dnf install` en Fedora, o `pacman -S` en Arch Linux).

### **i. top**

- **Funcionamiento:** Muestra una lista de los procesos que más consumen recursos en tiempo real, de forma interactiva. Es ideal para monitorear el estado del sistema.
- **Parámetros:** No se usa con parámetros de línea de comandos comunes, ya que sus opciones se manejan desde la interfaz interactiva (`k` para `kill`, `q` para salir, `P` para ordenar por CPU, etc.).
- **Ubicación:** Generalmente en `/usr/bin/top`.

### **ii. htop**

- **Funcionamiento:** Una versión mejorada y más amigable de `top`. Proporciona una interfaz a color con gráficos de uso de CPU y memoria, y permite manipular procesos con mayor facilidad.
- **Parámetros:** La mayoría de las opciones se manejan de forma interactiva (ej. F6 para ordenar, F9 para `kill`). Se puede usar `htop -u <usuario>` para ver los procesos de un usuario específico.
- **Ubicación:** Generalmente en `/usr/bin/htop`. A menudo no viene por defecto.

### **iii. ps**

- **Funcionamiento:** Muestra un "snapshot" (una foto estática) de los procesos en ejecución en un momento dado. A diferencia de `top`, no se actualiza en tiempo real.
- **Parámetros:**
    - `ps aux`: Muestra todos los procesos de todos los usuarios en el sistema.
    - `ps -ef`: Muestra una salida similar con más detalles, usando un formato de estilo `BSD` y `System V` respectivamente.
    - `ps -p <PID>`: Muestra información sobre un PID específico.
- **Ubicación:** Generalmente en `/usr/bin/ps`.

### **iv. pstree**

- **Funcionamiento:** Muestra los procesos en un formato de árbol, reflejando la jerarquía padre-hijo.
- **Parámetros:**
    - `pstree`: Muestra el árbol de procesos completo.
    - `pstree -p`: Muestra los PID de cada proceso en el árbol.
    - `pstree <PID>`: Muestra el árbol de procesos que desciende de un PID específico.
- **Ubicación:** Generalmente en `/usr/bin/pstree`.

### **v. kill**

- **Funcionamiento:** Envía una señal a un proceso para controlarlo. La señal más común es `SIGTERM` (terminar) o `SIGKILL` (terminar forzadamente).
- **Parámetros:**
    - `kill <PID>`: Envía la señal `SIGTERM` por defecto, que le pide al proceso que se termine de forma limpia.
    - `kill -9 <PID>`: Envía la señal `SIGKILL`, que termina el proceso de forma forzada e inmediata.
- **Ubicación:** Generalmente en `/bin/kill`.

### **vi. pgrep**

- **Funcionamiento:** Busca procesos basándose en su nombre u otros atributos y devuelve sus PID.
- **Parámetros:** `pgrep <nombre_proceso>`. Por ejemplo, `pgrep firefox` devuelve el PID del proceso de Firefox.
- **Ubicación:** Generalmente en `/usr/bin/pgrep`.

### **vii. pkill**

- **Funcionamiento:** Busca procesos basándose en su nombre y les envía una señal. Es una combinación de `pgrep` y `kill`.
- **Parámetros:** `pkill <nombre_proceso>`. Por ejemplo, `pkill firefox` termina todos los procesos de Firefox. `pkill -9 firefox` los termina forzadamente.
- **Ubicación:** Generalmente en `/usr/bin/pkill`.

### **viii. killall**

- **Funcionamiento:** Termina todos los procesos con un nombre determinado. Al igual que `pkill`, es una herramienta muy potente.
- **Parámetros:**
    - `killall <nombre_proceso>`: Envía la señal `SIGTERM` a todos los procesos con ese nombre.
    - `killall -9 <nombre_proceso>`: Envía la señal `SIGKILL` de forma forzada.
- **Ubicación:** Generalmente en `/usr/bin/killall`.

### **ix. renice**

- **Funcionamiento:** Cambia la prioridad de un proceso en ejecución. La prioridad, conocida como **valor nice**, va de -20 (más alta) a 19 (más baja). Un valor más bajo significa que el proceso recibirá más tiempo de CPU.
- **Parámetros:**
    - `renice <valor_nice> -p <PID>`: Cambia la prioridad de un PID específico.
    - `renice -n <valor_nice> <PID>`: Otro formato común.
- **Ubicación:** Generalmente en `/usr/bin/renice`.

### **x. xkill**

- **Funcionamiento:** Una herramienta gráfica para terminar procesos de ventanas. Al ejecutar el comando, el cursor cambia a un cráneo o a una "X", y al hacer clic en una ventana, el proceso asociado se termina.
- **Parámetros:** No tiene parámetros de línea de comandos comunes, ya que su uso es interactivo y gráfico.
- **Ubicación:** Generalmente en `/usr/bin/xkill`.

### **xi. atop**

- **Funcionamiento:** Un monitor de procesos y rendimiento del sistema en tiempo real. Proporciona una visión completa del uso de recursos, incluyendo CPU, memoria, disco y red, mostrando los procesos que los utilizan.
- **Parámetros:** Se ejecuta simplemente con `atop`. Las opciones interactivas (`a`, `d`, `n`) permiten alternar la vista de recursos.
- **Ubicación:** Generalmente en `/usr/bin/atop`. No viene por defecto en la mayoría de las distribuciones.

### **xii. nice**

- **Funcionamiento:** Inicia un nuevo proceso con una prioridad específica (valor nice).
- **Parámetros:**
    - `nice -n <valor_nice> <comando>`: Inicia el comando con la prioridad especificada. Por ejemplo, `nice -n 19 <comando>` para ejecutarlo con la menor prioridad posible.
- **Ubicación:** Generalmente en `/usr/bin/nice`.

---

# 13.

### a. Pasos del proceso de inicio de un sistema GNU/Linux

El proceso de arranque de un sistema GNU/Linux, desde que se enciende el equipo hasta el login, se puede resumir en los siguientes pasos:

1. **BIOS/UEFI:** Al encender, el firmware del sistema (BIOS o UEFI) se ejecuta, realiza una verificación del hardware (POST) y busca un dispositivo de arranque.
2. **Cargador de arranque (Bootloader):** El firmware carga el cargador de arranque (como **GRUB** o **LILO**) del disco duro. El bootloader muestra un menú, carga el kernel de Linux y un **initramfs** (un sistema de archivos inicial en memoria).
3. **Kernel de Linux:** El kernel se carga en memoria y toma el control. Inicializa el hardware, monta el sistema de archivos raíz y, finalmente, ejecuta el primer proceso del sistema, **init**.
4. **Proceso INIT:** `init` (o `systemd` en la mayoría de las distribuciones modernas) es el primer proceso con **PID 1**. Lee sus archivos de configuración (`/etc/inittab` en el caso de SystemV) para determinar el **runlevel** (nivel de ejecución) predeterminado y ejecuta los scripts de inicialización correspondientes para arrancar los servicios del sistema.
5. **Runlevels (Niveles de ejecución):** Los scripts de los runlevels inician servicios como la red, los servidores de archivos, los servidores web, etc.
6. **Login:** Una vez que todos los servicios necesarios para el runlevel seleccionado se han iniciado, el sistema muestra el prompt de inicio de sesión (`login`) en una consola virtual o inicia la interfaz gráfica de usuario.

---

### b. Proceso INIT

- **¿Quién lo ejecuta?** El **kernel de Linux** es el encargado de ejecutar el proceso `init` como el primer proceso del sistema, con PID 1.
- **¿Cuál es su objetivo?** El objetivo de `init` es actuar como el padre de todos los demás procesos del sistema. Gestiona la transición entre los diferentes runlevels y es el responsable de adoptar a los procesos "huérfanos" (aquellos cuyo padre ha terminado) para que no se conviertan en procesos zombis. Su función principal es asegurar que el sistema alcance un estado de funcionamiento definido.

---

### c. Runlevels

- **¿Qué son?** Los runlevels, o **niveles de ejecución**, son estados del sistema predefinidos que determinan qué servicios y procesos deben estar activos. Cada runlevel representa un modo de operación diferente, desde un modo de rescate mínimo hasta un modo multiusuario completo con entorno gráfico.
- **¿Cuál es su objetivo?** Su objetivo principal es ofrecer una forma estructurada de iniciar, detener y reiniciar servicios para cambiar entre los diferentes modos de operación del sistema de manera segura y controlada.

---

### d. Referencia de los Runlevels y su configuración

- **Referencia de cada nivel:**
    - **Runlevel 0:** Apagado del sistema.
    - **Runlevel 1 (S):** Modo de usuario único (single-user mode) o modo de rescate. No hay servicios de red ni multiusuario, ideal para tareas de mantenimiento.
    - **Runlevel 2:** Modo multiusuario sin soporte de red (generalmente utilizado en sistemas de servidor).
    - **Runlevel 3:** Modo multiusuario completo con red. Es el modo estándar para los servidores sin entorno gráfico.
    - **Runlevel 4:** No está definido de forma estándar, se deja para personalizaciones.
    - **Runlevel 5:** Modo multiusuario completo con interfaz gráfica de usuario. Es el modo predeterminado para la mayoría de las distribuciones de escritorio.
    - **Runlevel 6:** Reinicio del sistema.
- **¿Dónde se define?** El runlevel predeterminado al iniciar el sistema se define en el archivo de configuración `/etc/inittab`. La línea `id:X:initdefault:` establece el runlevel por defecto, donde `X` es el número del runlevel.
- **¿Respetan los estándares?** **No, no todas las distribuciones respetan estos estándares.** El sistema **SystemV init**, que usa runlevels, ha sido reemplazado en la mayoría de las distribuciones modernas (como Debian, Ubuntu, CentOS, Fedora) por **`systemd`**, que utiliza "targets" en lugar de runlevels, aunque mantiene la compatibilidad con los conceptos de runlevel para evitar problemas de retrocompatibilidad.

---

### e. Archivo /etc/inittab

- **¿Cuál es su finalidad?** La finalidad del archivo `/etc/inittab` es configurar el comportamiento del proceso `init`. Le dice a `init` qué hacer cuando se inicia, qué procesos ejecutar en cada runlevel y cómo manejar los apagados y reinicios.
- **¿Qué tipo de información almacena?** Almacena información sobre el runlevel por defecto, los procesos que deben ser ejecutados una sola vez (ej. `sysinit`), los procesos que se ejecutan al entrar a cada runlevel y las acciones a tomar en caso de eventos del sistema (ej. fallo de energía o apagado por Ctrl+Alt+Del).
- **Estructura de la información:** Cada línea en `/etc/inittab` tiene la siguiente estructura:
    
    `id:runlevels:action:process`
    
    - `id`: Un identificador único de 1 a 4 caracteres para la entrada.
    - `runlevels`: Los runlevels en los que la acción se debe ejecutar.
    - `action`: La acción que `init` debe tomar (ej. `respawn`, `wait`, `once`, `initdefault`).
    - `process`: El comando o script que se debe ejecutar.

---

### f. Cambio de runlevel

- **Comandos para cambiar de runlevel:** Para cambiar de un runlevel `<X>` a un runlevel `<Y>`, se usa el comando **`init`** seguido del número del nuevo runlevel.
    - Ejemplo: Para pasar al modo multiusuario con red (runlevel 3), se ejecuta:Bash
        
        `sudo init 3`
        
- **¿Es un cambio permanente?** **No, este cambio no es permanente.** El cambio realizado con `init` solo afecta la sesión actual. Al reiniciar el sistema, volverá al runlevel que está definido en el archivo `/etc/inittab` como el predeterminado. Para hacer el cambio permanente, se debe modificar el archivo `/etc/inittab` y cambiar el `id:X:initdefault:` al nuevo runlevel deseado.

---

### g. Scripts RC (Runlevel Control)

- **Finalidad:** Los scripts RC son scripts de shell que se encargan de iniciar o detener los servicios (demonios) del sistema cuando se cambia a un runlevel específico.
- **Ubicación:** Se almacenan en directorios de control de runlevel, como `/etc/rc.d` o `/etc/rcN.d`, donde `N` es el número del runlevel (ej. `/etc/rc3.d` para el runlevel 3).
- **Determinación de qué script ejecutar:** Cuando el sistema cambia a un runlevel, `init` busca los scripts en el directorio `rcN.d` correspondiente. Los nombres de los scripts en estos directorios son enlaces simbólicos a los scripts de inicio reales (`/etc/init.d/`). El nombre del enlace simbólico determina si el servicio se inicia o se detiene:
    - Los nombres que comienzan con **`S`** (de **`Start`**) se ejecutan para iniciar el servicio.
    - Los nombres que comienzan con **`K`** (de **`Kill`**) se ejecutan para detener el servicio.
    - El número que sigue a la `S` o a la `K` determina el orden de ejecución. Por ejemplo, `S20nombre` se ejecutará antes que `S80nombre`.
- **Orden de llamada:** **Sí, existe un orden para llamarlos.** El orden de ejecución está dado por el número que se encuentra en el nombre del enlace simbólico. Esto es crucial para asegurar que los servicios dependientes se inicien en el orden correcto. Por ejemplo, el servicio de red (`S10network`) debe iniciarse antes que el servicio web (`S80apache`), ya que este último depende de la red para funcionar.

---

# 14. SystemD

### a. ¿Qué es SystemD?

**SystemD** es un sistema de inicio (init system) y un gestor de servicios para el kernel de Linux. Es el reemplazo moderno de los antiguos sistemas de arranque como **SystemV init** y **Upstart**. Su objetivo principal es inicializar los componentes del espacio de usuario que se necesitan después de que el kernel ha sido cargado, y además, gestionar los servicios, demonios y montajes de forma concurrente, lo que resulta en un arranque mucho más rápido del sistema.

---

### b. ¿A qué hace referencia el concepto de Unit?

En SystemD, el concepto de **Unit** hace referencia a un archivo de configuración que define un recurso o un servicio que SystemD puede gestionar. Una `unit` es la unidad básica de control de SystemD. Existen varios tipos de unidades, siendo los más comunes:

- **Service units (`.service`):** Definen un servicio del sistema, como un servidor web (`apache2.service`) o un servidor de base de datos (`mysql.service`).
- **Mount units (`.mount`):** Controlan los puntos de montaje del sistema de archivos.
- **Target units (`.target`):** Sirven para agrupar otras unidades y replicar el concepto de runlevels de SystemV.
- **Device units (`.device`):** Representan un dispositivo de hardware conectado al sistema.

---

### c. ¿Para qué sirve el comando `systemctl`?

El comando `systemctl` es la principal herramienta para controlar y gestionar SystemD. Permite interactuar con el sistema de inicio y los servicios. Se utiliza para:

- **Controlar servicios:** Iniciar, detener, reiniciar, o recargar servicios.
- **Habilitar/deshabilitar servicios:** Configurar si un servicio debe iniciarse automáticamente al arrancar el sistema.
- **Verificar el estado:** Comprobar el estado actual de una unidad.
- **Gestionar targets:** Cambiar entre los diferentes targets (equivalentes a runlevels).

Por ejemplo, `sudo systemctl start apache2` inicia el servicio de Apache, mientras que `sudo systemctl status apache2` muestra su estado.

---

### d. ¿A qué hace referencia el concepto de Target?

El concepto de **Target** en SystemD es una forma de agrupar unidades de servicio y otros targets para lograr un estado del sistema específico. Son el reemplazo de los runlevels de SystemV. Un `target` define un conjunto de servicios que deben estar en ejecución para que el sistema esté en un estado particular.

- `multi-user.target`: Es el equivalente al runlevel 3 (modo multiusuario con red).
- `graphical.target`: Es el equivalente al runlevel 5 (modo multiusuario con interfaz gráfica).
- `reboot.target`: El estado de reinicio.
- `poweroff.target`: El estado de apagado.

Cada target tiene una lista de dependencias que le dicen a SystemD qué unidades debe iniciar para alcanzar ese estado.

---

### e. Ejecutar el comando `pstree`

Al ejecutar el comando `pstree` en un sistema que utiliza SystemD, se puede observar una estructura de árbol de procesos donde la raíz es **`systemd`** (PID 1). Todos los demás procesos del sistema son ramas de este árbol, ya que SystemD es el proceso padre de todos los demás.

El `pstree` en un sistema moderno muestra claramente la jerarquía de procesos iniciada y gestionada por SystemD, a diferencia de los sistemas antiguos donde la raíz del árbol de procesos era `init`.

---

# 15. Usuarios

### a. Archivos de información de usuarios

En un sistema GNU/Linux, la información de los usuarios y los grupos se almacena principalmente en dos archivos:

- **`/etc/passwd`**: Almacena información sobre las cuentas de usuario, incluyendo el nombre de usuario, el ID de usuario (UID), el ID de grupo principal (GID), el directorio de inicio (`home directory`), y el shell predeterminado. La contraseña se solía almacenar aquí, pero por motivos de seguridad, ahora se guarda en un archivo separado.
- **`/etc/shadow`**: Contiene la información de la contraseña encriptada de los usuarios y las políticas de vencimiento de contraseñas. Este archivo solo puede ser leído por el usuario `root` para mayor seguridad.

---

### b. UID y GID

- **UID (User ID):** Es un número único que identifica a cada usuario en el sistema. Es la forma en que el kernel de Linux y los procesos identifican al propietario de un archivo o proceso.
- **GID (Group ID):** Es un número único que identifica a cada grupo de usuarios en el sistema. Los permisos de acceso a archivos y directorios pueden ser gestionados a nivel de grupo.
- **¿Pueden coexistir UIDs iguales?** No. Los UIDs deben ser únicos en un sistema para que el sistema de archivos y el kernel puedan distinguir de forma inequívoca a los propietarios de los archivos y los procesos. Si dos usuarios tuvieran el mismo UID, el sistema los trataría como la misma entidad, lo cual podría llevar a graves problemas de seguridad y de gestión de permisos.

---

### c. Usuario `root`

- **¿Qué es el usuario `root`?** El usuario `root` es el **superusuario** en sistemas tipo UNIX y GNU/Linux. Es la cuenta de administración que tiene privilegios absolutos sobre el sistema. Puede realizar cualquier tarea, como instalar software, modificar archivos del sistema, y gestionar permisos, sin restricciones.
- **¿Puede existir más de un usuario con este perfil?** En esencia, no. Solo puede haber un usuario con el UID 0. Sin embargo, se pueden crear otros usuarios con UID 0 de forma manual. Esto no es recomendable, ya que es una práctica de seguridad muy pobre. La forma segura y estándar de otorgar privilegios de `root` es a través del comando `sudo`.
- **¿Cuál es la UID de `root`?** La UID de `root` es siempre **0**. Este es un estándar universal en sistemas GNU/Linux y UNIX.

---

### d. Gestión de usuario `isocso`

A continuación se presenta el proceso paso a paso para realizar las acciones solicitadas:

1. **Crear el grupo `informatica`:**Bash
    
    `sudo groupadd informatica`
    
2. **Crear el usuario `isocso`:**Bash
    
    `sudo useradd -m -d /home/isocso -g informatica isocso`
    
    - `m`: Crea el directorio de inicio (`/home/isocso`).
    - `d /home/isocso`: Especifica la ubicación del directorio de inicio.
    - `g informatica`: Asigna el grupo `informatica` como el grupo principal del usuario.
3. **Crear un archivo en el `home` del usuario:** Dado que no se ha iniciado sesión, se debe usar `sudo` y el comando `touch` para crear el archivo y luego `chown` para cambiar el propietario.Bash
    
    `sudo touch /home/isocso/mi_archivo.txt
    sudo chown isocso:informatica /home/isocso/mi_archivo.txt`
    
    - `chown`: cambia el propietario y el grupo del archivo.
4. **Borrar el usuario y verificar su eliminación:**Bash
    
    `sudo userdel -r isocso`
    
    - `r`: Elimina el directorio de inicio del usuario y su cola de correo.
    - Verificación: Para confirmar que no queden registros, se pueden usar los comandos `grep` y `cat`:Bash
        
        `grep isocso /etc/passwd
        grep isocso /etc/shadow
        grep informatica /etc/group`
        
        Si los comandos no devuelven ninguna salida para `isocso` y el directorio `/home/isocso` ya no existe, el usuario ha sido eliminado correctamente.
        

---

### e. Comandos de gestión de usuarios y grupos

- **`useradd` y `adduser`**:
    - **`useradd`**: Es un comando de bajo nivel que crea una nueva cuenta de usuario. Es más manual y requiere especificar los parámetros como el directorio de inicio, el shell, etc., con opciones de línea de comandos. Se usa principalmente en scripts.
    - **`adduser`**: Es un `script` de alto nivel que interactúa con el usuario, guiándolo a través de la creación de la cuenta de forma más amigable, solicitando información como el nombre completo, la contraseña, etc. A menudo se encarga automáticamente de crear el directorio de inicio y otros detalles.
    - **Ubicación**: `/usr/sbin/useradd`, `/usr/sbin/adduser`.
- **`usermod`**:
    - **Funcionalidad**: Permite modificar los atributos de una cuenta de usuario existente.
    - **Parámetros**: `l` para cambiar el nombre de usuario, `d` para cambiar el directorio de inicio, `g` para cambiar el grupo principal, `aG` para agregar un usuario a grupos secundarios.
    - **Ubicación**: `/usr/sbin/usermod`.
- **`userdel`**:
    - **Funcionalidad**: Elimina una cuenta de usuario.
    - **Parámetros**: `r` para eliminar el directorio de inicio y el correo del usuario junto con la cuenta.
    - **Ubicación**: `/usr/sbin/userdel`.
- **`su`**:
    - **Funcionalidad**: Cambia el usuario efectivo actual por otro. Se usa comúnmente para convertirse en `root` o en otro usuario.
    - **Parámetros**: `su - <usuario>` inicia una sesión de `login` completa con el entorno del usuario, mientras que `su <usuario>` solo cambia la identidad del usuario sin cambiar el entorno.
    - **Ubicación**: `/bin/su`.
- **`groupadd`**:
    - **Funcionalidad**: Crea un nuevo grupo de usuarios.
    - **Parámetros**: `g` para especificar un GID, `r` para crear un grupo de sistema.
    - **Ubicación**: `/usr/sbin/groupadd`.
- **`who`**:
    - **Funcionalidad**: Muestra una lista de los usuarios que están actualmente conectados al sistema.
    - **Parámetros**: `who -b` muestra la hora del último arranque del sistema, `who -r` muestra el runlevel actual.
    - **Ubicación**: `/usr/bin/who`.
- **`groupdel`**:
    - **Funcionalidad**: Elimina un grupo de usuarios.
    - **Parámetros**: No tiene opciones comunes más allá de la de ayuda. Solo se puede borrar un grupo si no tiene miembros.
    - **Ubicación**: `/usr/sbin/groupdel`.
- **`passwd`**:
    - **Funcionalidad**: Permite a un usuario cambiar su propia contraseña. `root` puede cambiar la contraseña de cualquier usuario.
    - **Parámetros**: `passwd <usuario>` para cambiar la contraseña de otro usuario (requiere privilegios de `root`).
    - **Ubicación**: `/usr/bin/passwd`.

---

# 16. FileSystem y permisos

### a. ¿Cómo son definidos los permisos sobre archivos en un sistema GNU/Linux?

En un sistema GNU/Linux, los permisos sobre archivos y directorios se definen para tres categorías de usuarios:

1. **Usuario (`u`):** El propietario del archivo.
2. **Grupo (`g`):** El grupo de usuarios al que pertenece el archivo.
3. **Otros (`o`):** Todos los demás usuarios del sistema.

Para cada una de estas categorías, se pueden asignar tres tipos de permisos:

- **Lectura (`r`):** Permite ver el contenido de un archivo o listar los archivos en un directorio.
- **Escritura (`w`):** Permite modificar o eliminar un archivo, o crear, eliminar y renombrar archivos en un directorio.
- **Ejecución (`x`):** Permite ejecutar un archivo (si es un programa o script) o entrar a un directorio.

Los permisos se visualizan con el comando `ls -l` y se representan con 10 caracteres, donde el primero indica el tipo de archivo y los 9 restantes los permisos (ej. `-rwxr-xr-x`).

---

### b. Comandos de gestión de permisos

- **`chmod` (change mode):**
    - **Funcionalidad:** Cambia los permisos de acceso de archivos y directorios.
    - **Parámetros:** Se puede usar notación simbólica (ej. `chmod u+x mi_script.sh`) o notación octal (ej. `chmod 755 mi_script.sh`).
- **`chown` (change owner):**
    - **Funcionalidad:** Cambia el propietario de un archivo o directorio. Solo `root` puede cambiar el propietario de un archivo que no le pertenece.
    - **Parámetros:** `chown nuevo_propietario archivo`. Se puede cambiar también el grupo con `chown nuevo_propietario:nuevo_grupo archivo`.
- **`chgrp` (change group):**
    - **Funcionalidad:** Cambia el grupo de un archivo o directorio.
    - **Parámetros:** `chgrp nuevo_grupo archivo`.

---

### c. Notación octal en `chmod`

La notación octal es una forma numérica de representar los permisos. Cada permiso tiene un valor numérico:

- Lectura (`r`): **4**
- Escritura (`w`): **2**
- Ejecución (`x`): **1**
- Ningún permiso (): **0**

Cada dígito en la notación octal de tres dígitos representa la suma de los permisos para una categoría:

- **Primer dígito:** Permisos para el **usuario propietario**.
- **Segundo dígito:** Permisos para el **grupo**.
- **Tercer dígito:** Permisos para los **otros**.

**Ejemplo:**

- `chmod 755 archivo.sh`
    - `7` (4+2+1): Permiso `rwx` para el usuario.
    - `5` (4+0+1): Permiso `r-x` para el grupo.
    - `5` (4+0+1): Permiso `r-x` para otros.

---

### d. Acceso a archivos sin permisos

Sí, existe la posibilidad de que un usuario sin permisos pueda acceder a un archivo. El usuario **`root`**, al ser el superusuario, **puede acceder a cualquier archivo y directorio** del sistema sin importar los permisos establecidos para el usuario, el grupo o los otros. Es la excepción a las reglas de permisos, ya que su UID 0 le otorga acceso absoluto.

**Prueba:**

1. Cree un archivo como un usuario normal y elimine todos los permisos para otros:Bash
    
    `touch archivo_prueba.txt
    chmod 700 archivo_prueba.txt
    ls -l archivo_prueba.txt`
    
    La salida mostrará `-rwx------`, indicando que solo el propietario tiene permisos.
    
2. Intente leer el archivo como un usuario diferente (que no sea `root`):Bash
    
    `sudo -u otro_usuario cat archivo_prueba.txt`
    
    Esto fallará con un mensaje de "Permiso denegado".
    
3. Ahora intente leer el archivo como `root`:Bash
    
    `sudo cat archivo_prueba.txt`
    
    El comando se ejecutará sin problemas, demostrando que `root` puede ignorar los permisos.
    

---

### e. “Full Path Name” (Path Absoluto) y “Relative Path Name” (Path Relativo)

- **Full Path Name (Path Absoluto):** Es la ruta completa de un archivo o directorio, comenzando siempre desde el directorio raíz (`/`). Es una ruta inequívoca que no depende del directorio actual del usuario.
    - **Ejemplos:** `/home/usuario/documentos/reporte.txt`, `/var/log/syslog`.
- **Relative Path Name (Path Relativo):** Es la ruta de un archivo o directorio que se especifica con respecto al directorio de trabajo actual. No comienza con `/`.
    - **Ejemplos:**
        - Si su directorio actual es `/home/usuario/documentos`, la ruta relativa a `reporte.txt` sería simplemente `reporte.txt`.
        - `../` se utiliza para moverse al directorio superior. Si se encuentra en `/home/usuario/documentos/`, la ruta relativa a `/home/usuario/` es `../`.
        - `./` se utiliza para referirse al directorio actual (ej. `./mi_script.sh`).

---

### f. Directorios y el `path`

- **Comando para saber la ubicación actual:** El comando `pwd` (Print Working Directory) muestra la ruta absoluta del directorio actual.
- **Acceder al directorio personal:** Sí, existe una forma muy simple. El carácter **`~`** (tilde) representa el directorio de inicio del usuario actual. Puede ingresar a su directorio personal ejecutando:Bash
    
    `cd ~`
    
    También puede usar `cd` sin argumentos.
    
- **Acceder a otros directorios:** Sí, puede utilizar la misma idea. El guion  representa el directorio en el que se encontraba justo antes. Si ha estado en `/var/log` y luego va a `/etc`, puede regresar a `/var/log` con:Bash
    
    `cd -`
    
    Esto es útil para alternar rápidamente entre dos ubicaciones.
    

---

### g. Comandos del FileSystem

- **`mount`:**
    - **Funcionalidad:** Monta un sistema de archivos, haciéndolo accesible desde el directorio de montaje especificado. Se usa para conectar dispositivos de almacenamiento como discos duros, pendrives, o particiones.
    - **Parámetros:** `mount /dev/sda1 /mnt/data`.
- **`umount`:**
    - **Funcionalidad:** Desmonta un sistema de archivos, lo que lo hace inaccesible y lo prepara para ser desconectado.
    - **Parámetros:** `umount /mnt/data`.
- **`du` (disk usage):**
    - **Funcionalidad:** Estima el uso de espacio en disco de archivos y directorios.
    - **Parámetros:** `du -h` para una salida legible por humanos, `du -sh` para un resumen del directorio actual.
- **`df` (disk free):**
    - **Funcionalidad:** Muestra la cantidad de espacio libre y usado en los sistemas de archivos montados.
    - **Parámetros:** `df -h` para una salida legible por humanos.
- **`mkfs` (make filesystem):**
    - **Funcionalidad:** Crea un sistema de archivos en una partición de disco. Se utiliza para formatear una partición.
    - **Parámetros:** `mkfs -t ext4 /dev/sda1` (crea un sistema de archivos ext4).
- **`fdisk` (disk partition table manipulator):**
    - **Funcionalidad:** Permite gestionar las particiones de un disco duro. Es una herramienta potente y peligrosa si no se usa con cuidado, ya que puede borrar datos de forma irreversible.
    - **Parámetros:** `fdisk /dev/sda`. El programa se ejecuta de forma interactiva.
- **`write`:**
    - **Funcionalidad:** Envía un mensaje a otro usuario que ha iniciado sesión en el mismo sistema. El mensaje aparece en su terminal.
    - **Parámetros:** `write nombre_usuario`.
- **`losetup`:**
    - **Funcionalidad:** Asocia un archivo a un dispositivo de bucle (loop device). Esto permite tratar un archivo regular como si fuera un dispositivo de bloque.
    - **Parámetros:** `losetup /dev/loop0 archivo.img`.
- **`stat`:**
    - **Funcionalidad:** Muestra el estado detallado de un archivo o directorio, incluyendo sus permisos, propietario, tamaño, marca de tiempo de modificación, y el número de `inodes`. Es muy útil para tareas de administración y scripts.
    - **Parámetros:** `stat archivo`.

---

# 17. Procesos

### a. Procesos en Foreground y Background

- **Foreground:** Un proceso que se ejecuta en **foreground** (primer plano) es el que interactúa directamente con el usuario a través de la terminal. Mientras se está ejecutando, la terminal está ocupada y no se pueden ejecutar otros comandos hasta que el proceso actual finalice.
- **Background:** Un proceso que se ejecuta en **background** (segundo plano) se ejecuta de manera silenciosa, sin ocupar la terminal, lo que permite al usuario seguir ejecutando otros comandos. Esto es ideal para tareas largas que no requieren interacción constante.

---

### b. Gestión de procesos en Foreground y Background

- **Ejecutar un proceso en background:** Para enviar un proceso a segundo plano, se debe agregar el símbolo de ampersand (`&`) al final del comando. Por ejemplo:Bash
    
    `comando_largo &`
    
    La terminal mostrará el PID (identificador del proceso) y el número del job, y liberará la línea de comandos inmediatamente.
    
- **Pasar de background a foreground:** Para traer un proceso de background al foreground, se usa el comando `fg`. Si hay varios procesos en segundo plano, se puede especificar el número del job.Bash
    
    `fg %1`
    
    El número del job se puede ver con el comando `jobs`.
    
- **Pasar de foreground a background:** Para enviar un proceso que ya está en primer plano a segundo plano, primero se debe detener con la combinación de teclas **Ctrl + Z**, y luego usar el comando `bg` para que continúe su ejecución en segundo plano.Bash
    
    `# (El proceso se está ejecutando)
    Ctrl + Z
    # (Proceso detenido)
    bg`
    

---

### c. Pipe (`|`)

- **Finalidad:** La **pipe** (`|`) es un operador que **redirige la salida estándar (stdout)** de un comando para que sea la **entrada estándar (stdin)** de otro. Su finalidad es encadenar comandos, creando flujos de datos complejos a partir de programas sencillos.
- **Ejemplos:**
    - **Paginación de la salida:** `ls -l /etc | less`
        - La salida de `ls -l /etc` (la lista de archivos en `/etc`) se envía como entrada al comando `less`, lo que permite navegar por la lista página por página.
    - **Filtrado de procesos:** `ps aux | grep firefox`
        - La salida completa del comando `ps aux` se filtra con `grep` para mostrar solo las líneas que contienen la palabra "firefox", lo que ayuda a encontrar el proceso de Firefox.

---

### d. Redirección

- **Finalidad:** La redirección es un mecanismo de los shells de comandos que permite cambiar la fuente de entrada estándar o el destino de la salida estándar o de error de un comando.
- **Tipos y ejemplos:**
    - **Redirección de salida (`>` y `>>`):** Envía la salida de un comando a un archivo en lugar de a la pantalla.
        - `>`: **Sobrescribe** el contenido del archivo si existe, o lo crea si no existe.Bash
            
            `echo "Hola Mundo" > saludo.txt  # El archivo 'saludo.txt' ahora contiene "Hola Mundo"`
            
        - `>>`: **Añade** la salida al final del archivo sin sobrescribirlo.Bash
            
            `echo "Adiós Mundo" >> saludo.txt  # El archivo 'saludo.txt' ahora contiene "Hola Mundo\nAdiós Mundo"`
            
    - **Redirección de entrada (`<`):** Obtiene la entrada estándar de un archivo en lugar de que el usuario la escriba por el teclado.Bash
        
        `wc -l < lista.txt  # Cuenta el número de líneas en el archivo 'lista.txt'`
        
    - **Redirección de error (2>):** Permite redirigir la salida de error estándar (stderr) a un archivo, separándola de la salida normal (stdout).Bash
        
        `find / -name mi_archivo 2> errores.log`
        
        - Este comando busca un archivo y, en lugar de mostrar los errores de "permiso denegado" en la pantalla, los guarda en el archivo `errores.log`.

---

# 18. Otros comandos linux

### a. Concepto de Empaquetar Archivos

En GNU/Linux, **empaquetar archivos** se refiere a la acción de agrupar varios archivos y/o directorios en un solo archivo. Este proceso no reduce el tamaño de los archivos, sino que los organiza de manera que sean más fáciles de almacenar, mover o transferir. Un paquete es, en esencia, un contenedor. El comando más utilizado para esta tarea es `tar`.

---

### b. Empaquetar y comparar tamaños

1. **Suma de tamaños:** Primero, seleccione 4 archivos y use el comando `ls -l` para ver sus tamaños individuales. Sume los tamaños para obtener el total.
2. **Crear el paquete:** Use el comando `tar` para empaquetar los archivos en un solo archivo con la extensión `.tar`.Bash
    
    `tar -cvf mi_paquete.tar archivo1.txt archivo2.txt archivo3.txt archivo4.txt`
    
    - `c`: Crea un nuevo archivo `.tar`.
    - `v`: Muestra el progreso (verbose).
    - `f`: Especifica el nombre del archivo de salida.
3. **Comparar tamaños:** Verifique el tamaño del archivo `.tar` recién creado.Bash
    
    `ls -l mi_paquete.tar`
    
    **Característica notable:** Notará que el tamaño del archivo empaquetado (`.tar`) es prácticamente la suma de los tamaños de los archivos individuales. Esto se debe a que el empaquetado no implica compresión; solo agrupa los archivos sin reducir su tamaño.
    

---

### c. Comprimir archivos en uno solo

Para comprimir 4 archivos en uno solo, la secuencia de comandos debe incluir un paso de empaquetado y luego un paso de compresión. Se recomienda primero empaquetar los archivos con `tar` y luego comprimir el archivo `.tar` con una herramienta como `gzip`.

1. **Empaquetar los archivos:**Bash
    
    `tar -cvf mis_archivos.tar archivo1.txt archivo2.txt archivo3.txt archivo4.txt`
    
2. **Comprimir el archivo empaquetado:**Bash
    
    `gzip mis_archivos.tar`
    
    El resultado será un archivo llamado `mis_archivos.tar.gz`. Si compara el tamaño de este archivo con el de `mis_archivos.tar`, verá una reducción significativa.
    

---

### d. Comprimir con un único comando

Sí, es posible empaquetar y comprimir un conjunto de archivos en uno solo utilizando un único comando. El comando `tar` tiene la capacidad de llamar a la herramienta de compresión directamente.

- **Con `gzip`:**Bash
    
    `tar -czvf mis_archivos.tar.gz archivo1.txt archivo2.txt archivo3.txt archivo4.txt`
    
    - `z`: Esta opción le dice a `tar` que comprima la salida con `gzip`.
- **Con `bzip2`:**Bash
    
    `tar -cjvf mis_archivos.tar.bz2 archivo1.txt archivo2.txt archivo3.txt archivo4.txt`
    
    - `j`: Le dice a `tar` que comprima la salida con `bzip2`.

---

### e. Funcionalidad de comandos

- **`tar`:**
    - **Funcionalidad:** Es una herramienta para archivar y empaquetar archivos. Se utiliza para agrupar múltiples archivos en un solo archivo contenedor (`.tar`).
    - **Parámetros principales:**
        - `c`: Crea un archivo.
        - `x`: Extrae archivos de un archivo.
        - `t`: Lista el contenido de un archivo.
        - `v`: Modo detallado (verbose).
        - `f`: Especifica el nombre del archivo.
        - `z`: Comprime/descomprime con `gzip`.
        - `j`: Comprime/descomprime con `bzip2`.
- **`grep`:**
    - **Funcionalidad:** Busca texto o patrones en archivos. Su nombre significa **G**lobal **R**egular **E**xpression **P**rint.
    - **Parámetros principales:**
        - `i`: Ignora mayúsculas/minúsculas.
        - `v`: Invierte la búsqueda (muestra las líneas que NO coinciden).
        - `n`: Muestra el número de línea.
        - `r`: Búsqueda recursiva en directorios.
- **`gzip`:**
    - **Funcionalidad:** Comprime o descomprime archivos utilizando el algoritmo `Lempel-Ziv`. Comprime un archivo y le agrega la extensión `.gz`.
    - **Parámetros principales:**
        - `d`: Descomprime un archivo.
        - `r`: Procesa recursivamente.
        - `c`: Escribe la salida a la salida estándar, no a un archivo.
- **`zgrep`:**
    - **Funcionalidad:** Es una variante de `grep` diseñada específicamente para buscar patrones de texto en archivos comprimidos con `gzip` (`.gz`). Esencialmente, es un script que descomprime el archivo temporalmente y luego ejecuta `grep` sobre su contenido.
    - **Parámetros principales:** Acepta los mismos parámetros que `grep`.
- **`wc`:**
    - **Funcionalidad:** Cuenta las líneas, palabras y bytes de un archivo o de una entrada estándar. Su nombre significa **W**ord **C**ount.
    - **Parámetros principales:**
        - `l`: Cuenta solo las líneas.
        - `w`: Cuenta solo las palabras.
        - `c`: Cuenta solo los bytes.

---

# 19. Ejemplos de comandos

A continuación se describe la acción de cada comando en el orden en que se ejecutan, asumiendo que se ejecutan como un usuario que no es `root` ni pertenece al grupo de `root`. Si un comando falla, se explica la razón.

---

### Análisis de los comandos

1. **`ls -l > prueba`**
    - **Acción:** Este comando lista el contenido del directorio actual en formato largo y redirige la salida a un archivo llamado **`prueba`**. Si el archivo no existe, se crea. Si ya existe, su contenido se sobrescribe.
    - **Resultado:** Se crea (o sobrescribe) un archivo llamado `prueba` en el directorio de trabajo del usuario.
2. **`ps > PRUEBA`**
    - **Acción:** Muestra los procesos en ejecución del usuario y **sobrescribe** el contenido de un nuevo archivo llamado **`PRUEBA`** con esta información.
    - **Resultado:** Se crea (o sobrescribe) un archivo llamado `PRUEBA`.
3. **`chmod 710 prueba`**
    - **Acción:** Cambia los permisos del archivo `prueba`.
        - `7` (4+2+1): Permisos `rwx` (lectura, escritura, ejecución) para el **usuario propietario**.
        - `1` (0+0+1): Permiso `x` (ejecución) para el **grupo**.
        - `0` (0+0+0): Ningún permiso para **otros**.
    - **Resultado:** El usuario cambia los permisos de su propio archivo `prueba` sin problema.
4. **`chown root:root PRUEBA`**
    - **Acción:** Intenta cambiar el propietario y el grupo del archivo `PRUEBA` a `root`.
    - **Resultado:** **Falla**. Un usuario no privilegiado no puede cambiar la propiedad de un archivo a otro usuario, ya que solo `root` tiene ese permiso. Se mostrará un mensaje de "Operación no permitida".
5. **`chmod 777 PRUEBA`**
    - **Acción:** Cambia los permisos del archivo `PRUEBA` para dar permisos de lectura, escritura y ejecución (`rwx`) a todos (usuario, grupo y otros).
    - **Resultado:** **Falla**. El usuario no puede cambiar los permisos del archivo `PRUEBA` porque no es el propietario, aunque lo haya creado.
6. **`chmod 700 /etc/passwd`**
    - **Acción:** Intenta cambiar los permisos del archivo `/etc/passwd`.
    - **Resultado:** **Falla**. `/etc/passwd` es un archivo de sistema propiedad de `root`. Un usuario normal no tiene permisos para modificarlo.
7. **`passwd root`**
    - **Acción:** Intenta cambiar la contraseña del usuario `root`.
    - **Resultado:** **Falla**. Solo el usuario `root` puede cambiar su propia contraseña. Un usuario normal no tiene los privilegios necesarios.
8. **`rm PRUEBA`**
    - **Acción:** Intenta eliminar el archivo `PRUEBA`.
    - **Resultado:** **Falla**. A pesar de que el usuario creó el archivo, no puede eliminarlo porque el comando `chown` intentó cambiar la propiedad a `root`, y aunque falló, los permisos del archivo no permiten la eliminación por parte de un usuario que no sea el propietario, lo que lo deja en un estado confuso, o bien si el `chown` funcionó en otra instancia, el usuario no es el propietario. Al no ser el propietario, no tiene permisos de escritura en el archivo, lo que impide su eliminación.
9. **`man /etc/shadow`**
    - **Acción:** Intenta abrir la página de manual del archivo `/etc/shadow`.
    - **Resultado:** **Falla**. El archivo `/etc/shadow` es un archivo de datos, no un comando o un archivo de configuración con una página de manual asociada. Se mostrará un mensaje de error como "No manual entry for /etc/shadow".
10. **`find / -name *.conf`**
    - **Acción:** Busca todos los archivos que terminan en `.conf` a partir del directorio raíz (`/`).
    - **Resultado:** Se ejecuta, pero con muchos errores. El usuario no tiene permisos de lectura en la mayoría de los directorios del sistema, por lo que el comando mostrará una larga lista de mensajes de "Permiso denegado".
11. **`usermod root -d /home/newroot -L`**
    - **Acción:** Intenta modificar el usuario `root`. Específicamente, intenta cambiar su directorio de inicio y bloquear su contraseña.
    - **Resultado:** **Falla**. La cuenta de `root` solo puede ser modificada por otro superusuario. El usuario actual no tiene los permisos para hacerlo.
12. **`cd /root`**
    - **Acción:** Intenta cambiar el directorio de trabajo al directorio de inicio de `root`.
    - **Resultado:** **Falla**. Por motivos de seguridad, los directorios de inicio de `root` no son accesibles para otros usuarios.
13. **`rm *`**
    - **Acción:** Intenta eliminar todos los archivos en el directorio actual.
    - **Resultado:** **Éxito**. El usuario tiene permisos para eliminar archivos en su propio directorio de trabajo. El archivo `prueba` sería eliminado en este paso.
14. **`cd /etc`**
    - **Acción:** Cambia el directorio de trabajo a `/etc`.
    - **Resultado:** **Éxito**. El directorio `/etc` es de acceso público para la lectura, por lo que el usuario puede entrar.
15. **`cp * /home -R`**
    - **Acción:** Intenta copiar de forma recursiva todos los archivos y directorios de `/etc` al directorio `/home`.
    - **Resultado:** **Falla**. Aunque el usuario puede leer el contenido de `/etc`, no tiene permisos para escribir en el directorio `/home` (que es propiedad de `root`), por lo que la operación de copia no se puede realizar.
16. **`shutdown`**
    - **Acción:** Intenta apagar el sistema.
    - **Resultado:** **Falla**. El comando `shutdown` requiere privilegios de `root` para ejecutarse. Un usuario normal no puede apagar o reiniciar el sistema.

---

# 20. Más ejemplos

Aquí están los comandos para realizar cada acción solicitada en un sistema GNU/Linux.

### a. Terminar el proceso con PID 23

Para terminar un proceso por su ID, se usa el comando `kill`.

Bash

`kill 23`

### b. Terminar el proceso llamado init o systemd

Para terminar el proceso `init` (en sistemas más antiguos) o `systemd` (en sistemas modernos) se usaría el comando `kill` o `killall`. Sin embargo, esto no es posible.

Bash

`killall systemd`

El resultado es un **error** de "Operación no permitida" o similar. Esto se debe a que `init` o `systemd` es el **proceso padre de todos los demás procesos** del sistema (PID 1), y el kernel de Linux impide su terminación para evitar que el sistema se bloquee o se vuelva inestable.

### c. Buscar todos los archivos de usuarios con “.conf” en su nombre

Para buscar archivos por nombre, se utiliza el comando `find`. La búsqueda se puede restringir a los directorios de usuarios.

Bash

`find /home -name "*.conf"`

El asterisco `*` es un comodín que representa cualquier secuencia de caracteres.

### d. Guardar una lista de procesos en el archivo /home/<su nombre de usuario>/procesos

Para obtener una lista de todos los procesos y guardarla en un archivo, se usa `ps` con redirección de salida.

Bash

`ps aux > /home/<su nombre de usuario>/procesos`

### e. Cambiar permisos del archivo `xxxx`

Los permisos solicitados son:

- Usuario: Lectura, escritura, ejecución (`rwx`, valor 7)
- Grupo: Lectura, ejecución (`r-x`, valor 5)
- Otros: Ejecución (`-x`, valor 1)

El valor total en notación octal es `751`. Se usa el comando `chmod`.

Bash

`chmod 751 /home/<su nombre de usuario>/xxxx`

### f. Cambiar permisos del archivo `yyyy`

Los permisos solicitados son:

- Usuario: Lectura, escritura (`rw-`, valor 6)
- Grupo: Lectura, ejecución (`r-x`, valor 5)
- Otros: Ninguno (`--`, valor 0)

El valor total en notación octal es `650`.

Bash

`chmod 650 /home/<su nombre de usuario>/yyyy`

### g. Borrar todos los archivos del directorio `/tmp`

Para eliminar todos los archivos y subdirectorios de `/tmp`, se usa el comando `rm` de forma recursiva y forzada.

Bash

`sudo rm -rf /tmp/*`

Se requiere `sudo` porque `/tmp` es un directorio del sistema.

### h. Cambiar el propietario del archivo `/opt/isodata` al usuario `isocso`

Para cambiar la propiedad de un archivo, se usa el comando `chown`. Se requieren permisos de `root`.

Bash

`sudo chown isocso /opt/isodata`

### i. Guardar el directorio actual en `/home/<su nombre de usuario>/donde` sin borrar el contenido

Para guardar el directorio actual, se usa `pwd` y se redirige la salida al archivo con el operador de **anexión** (`>>`) para no sobrescribir el contenido.

Bash

`pwd >> /home/<su nombre de usuario>/donde`