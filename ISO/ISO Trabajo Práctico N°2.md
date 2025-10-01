## a. ¿Qué es un Sistema Operativo?
Un **Sistema Operativo (SO)** es el software fundamental que gestiona los recursos de _hardware_ y proporciona servicios comunes para los programas de aplicación. Actúa como intermediario entre el usuario/aplicaciones y el _hardware_ de la computadora.
## b. Enumere qué componentes/aspectos del Hardware son necesarios para cumplir los objetivos de un sistema operativo
Para que un Sistema Operativo pueda cumplir sus objetivos de gestión y servicio, necesita interaccionar y controlar los siguientes aspectos o componentes principales del _hardware_:

- **Unidad Central de Procesamiento (CPU):** Es el "cerebro" de la computadora. El SO gestiona el tiempo de la CPU (planificación de procesos) para que los diferentes programas puedan ejecutarse.
    
- **Memoria Principal (RAM):** El SO administra el espacio de memoria, asignando porciones a los programas y asegurándose de que no interfieran entre sí.
    
- **Dispositivos de Entrada/Salida (E/S):** Incluyen teclado, ratón, pantalla, impresoras, discos duros, etc. El SO proporciona _drivers_ y mecanismos para controlar y coordinar el acceso a estos dispositivos.
    
- **Almacenamiento Secundario:** Discos duros (HDD/SSD). El SO implementa y gestiona el **Sistema de Archivos** para organizar y almacenar datos de forma persistente.
    
- **Controladores de Dispositivo:** Circuitos electrónicos que permiten a la CPU comunicarse con los dispositivos periféricos. El SO interactúa con ellos a través de _drivers_ (controladores de software).
    
- **Mecanismos de Protección:** Aspectos del _hardware_ (como modos de operación de la CPU o protección de memoria) que permiten al SO protegerse a sí mismo y a los diferentes programas de errores o accesos no autorizados.
## c. Enumere componentes de un Sistema Operativo
Los componentes principales que forman la estructura de un Sistema Operativo son:

1. **Núcleo (_Kernel_):** Es el corazón del SO. Realiza las funciones esenciales de bajo nivel, como:
    
    - Gestión de procesos (creación, planificación, finalización).
        
    - Gestión de memoria.
        
    - Gestión de E/S.
        
    - Manejo de interrupciones y llamadas al sistema.
        
2. **Sistema de Archivos:** Es el encargado de organizar, nombrar, almacenar y recuperar archivos en los dispositivos de almacenamiento.
    
3. **Gestor de Memoria:** Controla la memoria principal, decidiendo qué procesos se cargan en la RAM, dónde se ubican y cómo se protegen entre sí.
    
4. **Gestor de E/S (Entrada/Salida):** Se encarga de la comunicación entre el sistema y los dispositivos periféricos (a través de los _drivers_ o controladores de dispositivo).
    
5. **Planificador de Procesos/Tareas (_Scheduler_):** Determina qué proceso obtendrá el uso de la CPU en un momento dado, optimizando el rendimiento y la respuesta del sistema.
    
6. **Sistema de Protección y Seguridad:** Mecanismos para controlar el acceso a los recursos del sistema y evitar interferencias o daños (ej. gestión de permisos de usuario).
    
7. **Interfaz de Usuario (_Shell_ o GUI):** Es la forma en que el usuario interactúa con el SO. Puede ser una **Interfaz Gráfica de Usuario (GUI)** (como el escritorio de Windows o macOS) o una **Interfaz de Línea de Comandos (CLI)** (_shell_ de Linux/Unix).
    
8. **Utilidades del Sistema:** Programas que facilitan las tareas de mantenimiento y administración (ej. formateadores de disco, herramientas de diagnóstico, copias de seguridad).
## d.¿Que es una llamada al sistema (system call)? ¿Cómo es posible implementarlas?
Una **llamada al sistema** es el mecanismo mediante el cual un programa de aplicación solicita un servicio al **Sistema Operativo (SO)**, específicamente al **núcleo (_kernel_)**. Estos servicios incluyen la gestión de recursos de _hardware_ (como E/S de archivos, asignación de memoria, creación de procesos, etc.) a los que el programa no puede acceder directamente por motivos de seguridad y protección.

### Implementación

La implementación de una llamada al sistema se realiza de la siguiente manera:

1. **Transición de Modo:** El _hardware_ del procesador soporta al menos dos modos de operación: el **modo usuario** (donde se ejecutan las aplicaciones) y el **modo _kernel_/** _supervisor_ (donde se ejecuta el SO).
    
2. **Instrucción Especial:** El programa ejecuta una **instrucción de _hardware_** especial (como `TRAP` o **interrupción por _software_**) que cambia la CPU de **modo usuario a modo _kernel_**.
    
3. **Tabla de Llamadas:** Esta instrucción pasa un número que identifica el servicio específico solicitado (ej. leer un archivo, crear un proceso). El _kernel_ usa este número como índice en una **tabla de llamadas al sistema** para encontrar y ejecutar la rutina interna del SO correspondiente.
    
4. **Retorno:** Una vez finalizado el servicio, el _kernel_ devuelve el control al programa de usuario, cambiando la CPU de nuevo a **modo usuario**.
## e. Defina y diferencie Programa y proceso
|Característica|Programa|Proceso|
|---|---|---|
|**Definición**|Una **entidad pasiva** (conjunto de instrucciones y datos) almacenada en un disco.|Una **entidad activa** (programa en ejecución) que requiere recursos del sistema.|
|**Estado**|Estático e inmutable (excepto por actualización).|Dinámico, tiene un estado actual (ej. _Nuevo, Listo, Ejecución, Espera, Terminado_).|
|**Tiempo**|Persiste en el tiempo (almacenamiento).|Temporal, existe solo mientras se ejecuta.|
|**Recursos**|No consume recursos del sistema (CPU, RAM) directamente.|**Consume recursos del sistema** y requiere un contexto de ejecución.|
|**Ejemplo**|El archivo `.exe` o `.app` en el disco duro.|Una instancia de ese `.exe` que se ha cargado en memoria y se está ejecutando.|

- **Programa:** Es el código fuente o binario. Es un concepto estático.
    
- **Proceso:** Es una **instancia en ejecución** de un programa. Es un concepto dinámico que incluye el código, los datos, la pila (_stack_) y el estado actual de los registros de la CPU.
## f. ¿Cuál es la información mínima que el kernel debe tener sobre un proceso? ¿En que estructura de datos asociada almacena dicha información?
### Información Mínima Requerida por el Kernel

El _kernel_ necesita rastrear la siguiente **información mínima** sobre un proceso para poder gestionarlo y reanudar su ejecución correctamente:

1. **Identificador del Proceso (PID):** Un número único que identifica al proceso.
    
2. **Estado del Proceso:** El estado actual del proceso (_Nuevo, Listo, Ejecución, Espera, Terminado_).
    
3. **Contador de Programa (_Program Counter_):** La dirección de la próxima instrucción a ejecutar. **Esencial** para reanudar la ejecución.
    
4. **Registros de la CPU:** El contenido de todos los registros de la CPU, que deben ser guardados cuando el proceso es interrumpido. **Esencial** para el cambio de contexto (_context switch_).
    
5. **Información de Gestión de Memoria:** Punteros o direcciones a la tabla de páginas o segmentos del proceso.
    
6. **Información Contable/Recursos:** Tiempo de CPU usado y límites de recursos asignados.
    

### Estructura de Datos Asociada

Esta información se almacena en una estructura de datos dentro del _kernel_ llamada **Bloque de Control del Proceso (BCP)** o **PCB** (_Process Control Block_).

- El **PCB** es el repositorio de toda la información que el SO necesita para gestionar y rastrear un proceso.
    
- Existe **un PCB por cada proceso** en el sistema.
    
- El conjunto de todos los PCB es crucial para el funcionamiento del _kernel_, ya que es la principal herramienta para realizar la **planificación** y el **cambio de contexto**.
## g. ¿Qué objetivos persiguen los algoritmos de planificación (scheduling)?
Los algoritmos de planificación (o _scheduling_) persiguen optimizar la forma en que se asigna la **Unidad Central de Procesamiento (CPU)** a los procesos listos para ejecutarse. Sus objetivos principales varían según el entorno del sistema (por lotes, interactivo, tiempo real), pero generalmente buscan:

|Objetivo|Descripción|
|---|---|
|**Maximizar la Utilización de la CPU**|Mantener la CPU tan ocupada como sea posible.|
|**Maximizar la Productividad (_Throughput_)**|Aumentar el número de procesos completados por unidad de tiempo.|
|**Minimizar el Tiempo de Retorno (_Turnaround Time_)**|Reducir el tiempo total que tarda un proceso desde su llegada hasta su finalización.|
|**Minimizar el Tiempo de Espera**|Reducir el tiempo total que un proceso pasa en la cola de listos esperando por la CPU.|
|**Minimizar el Tiempo de Respuesta**|Reducir el tiempo que tarda el sistema en producir la primera respuesta al usuario (crucial en sistemas interactivos).|
|**Garantizar la Equidad (_Fairness_)**|Asegurar que cada proceso reciba una porción justa del tiempo de la CPU.|
## h. ¿Qué significa que un algoritmo de scheduling sea apropiativo o no apropiativo (Preemptive o Non-Preemptive)?
Esta distinción define cómo el algoritmo maneja la **reasignación de la CPU** una vez que un proceso ha comenzado a ejecutarse.

| Tipo de _Scheduling_                  | Significado                                                                                                                                                                                                                     | Comportamiento                                                                                                                                  |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **No Apropiativo (_Non-Preemptive_)** | Una vez que un proceso comienza a ejecutarse, **mantiene el control de la CPU** hasta que **termina** su ejecución o pasa voluntariamente al estado de _Espera_ (ej. para una operación de E/S).                                | No hay interrupciones forzadas por el _kernel_ basadas en tiempo o prioridad.                                                                   |
| **Apropiativo (_Preemptive_)**        | El proceso que se está ejecutando **puede ser interrumpido (apropiado)** en cualquier momento por el _kernel_ si un proceso de **mayor prioridad** llega o si el proceso actual ha excedido su **cuota de tiempo (_quantum_)**. | Permite una mejor **interactividad** y respuesta, ya que los procesos urgentes o nuevos no tienen que esperar a que el proceso actual finalice. |
## i. ¿Qué tareas realizan los siguientes módulos de planificación?: Short,Long y Medium term scheduler
El Sistema Operativo utiliza típicamente tres tipos de planificadores que operan en diferentes niveles de frecuencia y objetivos:
### i. Short Term Scheduler (Planificador a Corto Plazo)

- **Tarea:** Es el planificador más frecuente. Selecciona un proceso de la cola de **procesos listos** en la memoria principal y le asigna la **CPU**.
    
- **Frecuencia:** Muy alta (se ejecuta cada pocos milisegundos).
    
- **Objetivo Principal:** Maximizar la **utilización de la CPU** y minimizar el **tiempo de respuesta** (controla el flujo rápido).
    
- **Ubicación:** Opera entre los estados _Listo_ y _Ejecución_.
    

### ii. Long Term Scheduler (Planificador a Largo Plazo)

- **Tarea:** Controla el **grado de multiprogramación**. Decide qué trabajos o programas deben cargarse del almacenamiento secundario (disco) a la memoria principal para convertirse en **procesos listos**.
    
- **Frecuencia:** Baja (se ejecuta solo cuando un proceso termina o cuando se necesita mantener un equilibrio de la carga).
    
- **Objetivo Principal:** Seleccionar una mezcla equilibrada de procesos (E/S intensiva vs. CPU intensiva) para un uso eficiente de los recursos del sistema.
    
- **Ubicación:** Opera entre el almacenamiento (_Job Queue_) y el estado _Nuevo/Listo_.
    

### iii. Medium Term Scheduler (Planificador a Medio Plazo)

- **Tarea:** Es responsable de la **suspensión (_swapping out_)** y **reanudación (_swapping in_)** de procesos. Elimina temporalmente procesos de la memoria principal al almacenamiento secundario (y los devuelve más tarde) para reducir el grado de multiprogramación y liberar memoria.
    
- **Frecuencia:** Media (se ejecuta cuando el sistema está sobrecargado o necesita espacio de memoria).
    
- **Objetivo Principal:** Optimizar la **gestión de la memoria** y mejorar la mezcla de procesos en la memoria.
    
- **Ubicación:** Opera entre la memoria principal (RAM) y el disco (_Suspended Queue_).
## j. ¿Qué tareas realiza el Dispatcher?¿Y el Loader?
### Dispatcher (_Despachador_)

El _Dispatcher_ es el módulo que cede el control de la CPU al proceso seleccionado por el planificador a corto plazo (_Short Term Scheduler_). Sus tareas incluyen:

1. **Cambio de Contexto (_Context Switch_):** Guardar el estado (registros de CPU, Contador de Programa) del proceso que se va a interrumpir y cargar el estado del nuevo proceso seleccionado.
    
2. **Cambio de Modo de Usuario:** Cambiar la CPU del modo _kernel_ al modo usuario.
    
3. **Salto a la Ubicación Correcta:** Saltar a la dirección de memoria exacta (indicada por el Contador de Programa) donde debe reanudarse la ejecución del nuevo proceso.
    

El _Dispatcher_ debe ser lo más rápido posible, ya que se ejecuta en cada cambio de proceso (_Context Switch_).

### Loader (_Cargador_)

El _Loader_ es el componente del sistema operativo que se encarga de:

1. **Cargar el Programa:** Llevar el código y los datos de un programa desde el almacenamiento secundario (disco) a la **memoria principal (RAM)**.
    
2. **Preparación para la Ejecución:** Inicializar los registros de la CPU y las estructuras de gestión de memoria del proceso, preparando el entorno para que el programa pueda comenzar su ejecución como un proceso.
## k. ¿Qué significa que un proceso sea "CPU Bound" y "I/O Bound"?
La diferencia describe el tipo de recurso que más consume o limita la velocidad de un proceso:

|Tipo de Proceso|Significado|Características|Ejemplo|
|---|---|---|---|
|**CPU Bound** (Limitado por CPU)|Pasa la mayor parte de su tiempo **ejecutando cálculos** y realizando muy pocas operaciones de Entrada/Salida (E/S).|Su velocidad se limita por la **velocidad de la CPU**. Realizan ráfagas largas de uso de CPU.|Programas de cálculo científico, simulaciones complejas, renderizado de video, compiladores.|
|**I/O Bound** (Limitado por E/S)|Pasa la mayor parte de su tiempo **esperando** a que se completen las operaciones de Entrada/Salida.|Su velocidad se limita por la **velocidad de los dispositivos de E/S**. Realizan ráfagas muy cortas de uso de CPU.|Editores de texto, navegadores web, servidores de bases de datos que leen/escriben constantemente en disco.|

El _Scheduler_ busca equilibrar estos dos tipos para maximizar la utilización de la CPU (mientras los procesos _I/O Bound_ esperan, los _CPU Bound_ pueden ejecutar).

## l. ¿Cuáles son los estados posibles por los que puede atravesar un proceso? ¿Qué representa que un proceso se encuentre en los estados enumerados? Utilizando un diagrama explique las transiciones entre los estados.
Los procesos atraviesan una serie de estados que representan su actividad actual dentro del Sistema Operativo.

### Estados Posibles

1. **Nuevo (_New_):** El proceso está siendo creado.
    
    - **Representa:** El programa ha sido invocado y el SO está estableciendo sus estructuras de datos (PCB).
        
2. **Listo (_Ready_):** El proceso está esperando a que se le asigne la CPU.
    
    - **Representa:** El proceso reside en la memoria principal, tiene todos los recursos que necesita, y puede ejecutar su siguiente instrucción inmediatamente si la CPU estuviera disponible.
        
3. **Ejecución (_Running_):** El proceso está ejecutando instrucciones en la CPU.
    
    - **Representa:** Se están realizando las operaciones propias del código del programa. Solo puede haber un proceso en este estado por cada núcleo de CPU.
        
4. **Espera (_Waiting_):** El proceso está esperando a que ocurra algún evento (generalmente la finalización de una operación de E/S o la recepción de una señal).
    
    - **Representa:** El proceso no puede continuar, incluso si la CPU estuviera libre, hasta que se complete la operación externa solicitada.
        
5. **Terminado (_Terminated_):** El proceso ha finalizado su ejecución.
    
    - **Representa:** El SO está liberando los recursos del proceso (PCB, memoria) que ha completado su tarea.
        

### Diagrama de Transición de Estados

Las transiciones entre estados ocurren por eventos controlados por el SO:

- **1. Admisión:** El _Long Term Scheduler_ mueve el proceso de **Nuevo** a **Listo**.
    
- **2. Despacho (_Dispatch_):** El _Dispatcher_ mueve el proceso de **Listo** a **Ejecución** (asignación de CPU).
    
- **3. Interrupción/Expiración (_Interrupt_):** Si se acaba el _quantum_ de tiempo o llega un proceso de mayor prioridad, el SO mueve el proceso de **Ejecución** a **Listo** (Apropiación).
    
- **4. Espera de E/S:** El proceso solicita una E/S o espera un evento, moviéndose de **Ejecución** a **Espera**.
    
- **5. Fin de E/S:** El evento o la E/S que el proceso estaba esperando termina, moviéndolo de **Espera** a **Listo**.
    
- **6. Salida (_Exit_):** El proceso termina su ejecución de forma normal o anormal, moviéndose de **Ejecución** a **Terminado**.
## m. ¿Cuáles de los schedulers mencionados anteriormente se encargan de las transiciones entre los estados enumerados?
Los diferentes planificadores se encargan de gestionar las siguientes transiciones de estado:

| Planificador (_Scheduler_)      | Transiciones que Gestiona                                                      | Estados Involucrados                           |
| ------------------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------- |
| **Long Term Scheduler** (LTS)   | Admisión (cargar un trabajo).                                                  | **Nuevo** → **Listo**                          |
| **Short Term Scheduler** (STS)  | Despacho (asignar la CPU).                                                     | **Listo** → **Ejecución**                      |
| **Medium Term Scheduler** (MTS) | Suspensión/Reanudación (_Swapping_).                                           | **Listo** ⇌ **Suspendido/Espera** (Libera RAM) |
| **Dispatcher**                  | Cambios de estado por Expiración de _Quantum_ o Solicitud/Finalización de E/S. | **Ejecución** → **Listo** (Apropiación)        |
| **Kernel (Módulos de E/S)**     | Finalización de E/S/Evento.                                                    | **Espera** → **Listo**                         |
| **Kernel**                      | Salida.                                                                        | **Ejecución** → **Terminado**                  |
## n. Defina Tiempo de retorno (TR) y Tiempo de espera (TE) para un proceso.
Para un proceso individual:

- **Tiempo de Retorno (TR) o _Turnaround Time_:** Es el intervalo total de tiempo transcurrido desde que un proceso **llega** al sistema hasta que **termina** su ejecución. Mide la latencia total del proceso, incluyendo su tiempo de ejecución y todos los tiempos de espera.
    
    TR=Tiempo de Finalizacioˊn−Tiempo de Llegada
    
- **Tiempo de Espera (TE) o _Waiting Time_:** Es la cantidad total de tiempo que un proceso pasa en la cola de **Listo**, esperando ser asignado a la CPU. No incluye el tiempo que pasa en el estado _Espera_ (bloqueado por E/S).
    
    TE=Tiempo de Retorno−Tiempo de Ejecucioˊn de CPU

## o. Defina Tiempo Promedio de Retorno (TPR) y Tiempo promedio de espera (TPE) para un lote de procesos.
Estas métricas se aplican a un **conjunto o lote de n procesos** y se utilizan para evaluar la eficiencia global de un algoritmo de planificación.

![[Pasted image 20250925170034.png]]
## p. Defina tiempo de respuesta.
- **Tiempo de Respuesta (_Response Time_):** Es el tiempo transcurrido desde que un proceso **llega** al sistema hasta que **produce su primera respuesta** o comienza su primera ejecución.
    

Esta métrica es crucial para los **sistemas interactivos** (como los sistemas de escritorio), ya que mide la rapidez con la que el usuario percibe que el sistema está respondiendo a su solicitud.

Tiempo de Respuesta=Tiempo de la Primera Ejecucioˊn−Tiempo de Llegada

## 2. Para los siguientes algoritmos de scheduling:

➢​ FCFS (First Come First Served)

➢​ SJF (Shortest Job First)

➢​ Round Robin

➢​ Prioridades
## a.​ Explique su funcionamiento mediante un ejemplo.
Supongamos 3 procesos: **P1** (ráfaga de 24 ms, llegada en 0 ms), **P2** (ráfaga de 3 ms, llegada en 0 ms) y **P3** (ráfaga de 3 ms, llegada en 0 ms).

| Algoritmo                          | Funcionamiento                                                                                                                                                                                                                                               | Ejemplo (Orden de Ejecución)                                                                                                                                                       |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **FCFS** (First Come First Served) | **No expropiativo**. El proceso que llega primero es el primero en ser ejecutado. Se usa una cola **FIFO**.                                                                                                                                                  | Si llegan en orden **P1, P2, P3**: Se ejecuta P1 (0-24), luego P2 (24-27), luego P3 (27-30).                                                                                       |
| **SJF** (Shortest Job First)       | **Puede ser expropiativo o no expropiativo**. Se ejecuta el proceso con la ráfaga de CPU **más corta**. Minimiza el tiempo de espera promedio.                                                                                                               | Si todos llegan en 0 ms con ráfagas 24, 3, 3: Se ejecutarían **P2, P3, P1** (o P3, P2, P1) debido a que sus ráfagas son las más cortas.                                            |
| **Round Robin** (RR)               | **Expropiativo**. Cada proceso recibe un pequeño segmento de tiempo de CPU, llamado **Quantum** (q). Si el proceso no termina en ese tiempo, es interrumpido y se coloca al final de la cola de listos, esperando su siguiente turno. Usa una cola circular. | Con q=4 ms y ráfagas 24, 3, 3: Se rotan los procesos. P1 usa 4 ms, P2 usa 3 ms (termina), P3 usa 3 ms (termina), P1 usa 4 ms, y así sucesivamente hasta que P1 complete sus 24 ms. |
| **Prioridades**                    | **Puede ser expropiativo o no expropiativo**. Se asigna un valor de **prioridad** a cada proceso. El planificador elige el proceso con la prioridad más alta para ejecutar.                                                                                  | Si P1 (Prioridad 4), P2 (Prioridad 1), P3 (Prioridad 5). (Asumiendo que 1 es la más alta): Se ejecutaría **P2, P1, P3**.                                                           |
## b.​ ¿Alguno de ellos cuentan con parámetros para su funcionamiento? Identifique y enunciarlos
Solo dos de los algoritmos listados cuentan con un parámetro clave para su funcionamiento:

1. **Round Robin (RR):**
    
    - **Quantum de tiempo (q):** Es la unidad de tiempo (ej. milisegundos o _ticks_) que se le asigna a cada proceso para usar la CPU antes de ser forzado a ceder el turno al siguiente proceso en la cola.
        
2. **Prioridades:**
    
    - **Valor de Prioridad:** Es el valor numérico o cualitativo asignado a cada proceso, que determina su orden de ejecución. Un criterio común es que un número bajo indica una prioridad alta (o viceversa).
        
    - **(Opcional) Tasa de Envejecimiento (Aging Rate):** Este no es un parámetro directo del algoritmo simple, sino un mecanismo implementado para evitar la inanición. Consiste en aumentar dinámicamente la prioridad de los procesos que han esperado mucho tiempo.
        

**FCFS** y **SJF** (en su forma simple y no expropiativa) no requieren parámetros adicionales más allá del tiempo de llegada y el tiempo de ráfaga de CPU del proceso, respectivamente.
## c.​ Cual es el más adecuado según los tipos de procesos y/o SO.

|Algoritmo|Tipo de Proceso/SO Más Adecuado|Razón Principal|
|---|---|---|
|**FCFS**|Sistemas de **Procesamiento por Lotes (Batch)**.|Su simplicidad y baja sobrecarga administrativa lo hacen útil donde la respuesta rápida no es crítica. Sin embargo, no es adecuado para sistemas interactivos.|
|**SJF**|Sistemas de **Propósito General** o **Batch** (si se puede estimar la ráfaga).|Es teóricamente óptimo para minimizar el **tiempo promedio de espera** y el **tiempo promedio de retorno**. La versión expropiativa (**SRTF**) es mejor para entornos donde el proceso corto debe terminar rápido.|
|**Round Robin**|Sistemas de **Tiempo Compartido** o **Interactivos** (multiusuario/multitarea).|Su equidad y garantía de una porción de CPU para cada proceso resultan en un **buen tiempo de respuesta** para el usuario. Es el pilar de la planificación en SO modernos.|
|**Prioridades**|Sistemas de **Tiempo Real** o donde las tareas tienen **criticidad** variable.|Permite garantizar que los procesos vitales del sistema (alta prioridad) o los procesos sensibles al tiempo (tiempo real) sean ejecutados antes que los menos críticos.|
## d.​ Cite ventajas y desventajas de su uso.

|Algoritmo|Ventajas|Desventajas|
|---|---|---|
|**FCFS**|Muy **simple** de implementar. **Baja sobrecarga** de gestión (no requiere interrupciones de temporizador).|**Pobre rendimiento** en sistemas interactivos. Sufre del **efecto convoy** (un proceso largo bloquea a todos los demás).|
|**SJF**|**Óptimo** para minimizar el **tiempo de espera promedio** y el **tiempo de retorno promedio**.|**Difícil de implementar** porque requiere **predecir la duración de la próxima ráfaga** de CPU. Puede causar **inanición** (los procesos largos nunca se ejecutan si hay un flujo constante de procesos cortos).|
|**Round Robin**|**Equitativo** (fairness), garantizando el acceso a la CPU. **Buen tiempo de respuesta** en sistemas interactivos. Previene la inanición.|Introduce **sobrecarga por cambios de contexto** (si el quantum es muy pequeño). El **tiempo de retorno promedio** puede ser alto para procesos largos. El rendimiento depende críticamente de la elección del **quantum**.|
|**Prioridades**|Permite dar un **trato preferencial** a procesos críticos o sensibles al tiempo. Flexible para modelar otros algoritmos (SJF es un caso de prioridad).|El principal problema es la **inanición** (**starvation**) para los procesos de baja prioridad. Se requiere un mecanismo como el **envejecimiento (aging)** para mitigarla.|
## 3.
![[Pasted image 20250928143020.png]]
### i.
![[Pasted image 20250928143053.png]]

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 6   | 0   |
| 2    | 21  | 14  |
| 3    | 33  | 21  |
| 4    | 37  | 33  |
| 5    | 46  | 37  |
| PROM |     |     |
FORMULA te = tr - CPU
### ii.
![[Pasted image 20250928143208.png]]
sumo 1 a cada (contando el 0)???

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 10  | 3   |
| 2    | 46  | 31  |
| 3    | 31  | 19  |
| 4    | 4   | 0   |
| 5    | 19  | 10  |
| PROM |     |     |
### iii.
![[Pasted image 20250928143310.png]]
## 3b.
| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 22  |     |
| 2    |     |     |
| 3    |     |     |
| 4    |     |     |
| 5    |     |     |
| PROM |     |     |
