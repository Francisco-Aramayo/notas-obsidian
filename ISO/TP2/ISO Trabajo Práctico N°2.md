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

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 22  |     |
| 2    |     |     |
| 3    |     |     |
| 4    |     |     |
| 5    |     |     |
| PROM |     |     |

## 4. Dado el siguiente lote de procesos

| job | LLegada | Unidades de CPU |
| --- | ------- | --------------- |
| 1   | 0       | 4               |
| 2   | 2       | 6               |
| 3   | 3       | 4               |
| 4   | 6       | 5               |
| 5   | 8       | 2               |
### FCFS
![[Pasted image 20251006150849.png]]

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 4   | 0   |
| 2    | 8   | 2   |
| 3    | 11  | 7   |
| 4    | 13  | 8   |
| 5    | 13  | 11  |
| PROM | 9,8 | 5,6 |

### SJF
![[Pasted image 20251006151104.png]]

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 4   | 0   |
| 2    | 19  | 13  |
| 3    | 5   | 1   |
| 4    | 9   | 4   |
| 5    | 2   | 0   |
| PROM | 7,8 | 3,6 |

### RR q=1
![[Pasted image 20251006151130.png]]

| P    | TR   | TE  |
| ---- | ---- | --- |
| 1    | 7    | 0   |
| 2    | 17   | 11  |
| 3    | 14   | 10  |
| 4    | 15   | 10  |
| 5    | 8    | 6   |
| PROM | 12,2 | 7,4 |

### RR q=6
![[Pasted image 20251006151207.png]]

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 4   | 0   |
| 2    | 8   | 2   |
| 3    | 11  | 7   |
| 4    | 13  | 8   |
| 5    | 13  | 11  |
| PROM | 9,8 | 5,6 |
### c. En base a los tiempos calculados, compare los diferentes algoritmos

### d. En el algoritmo RR, que conclusión se puede sacar con respecto al valor del quantum?

### e. ¿Para el algoritmo Round Robin, en qué casos utilizará un valor dequantum alto y qué ventajas y desventajas obtendría?
### 💡 Si se usa un **quantum alto**:

Esto significa que cada proceso puede ejecutar durante más tiempo antes de ser interrumpido.

#### ✅ **Ventajas:**

1. **Menos cambios de contexto** → se reduce la sobrecarga del sistema (menos tiempo perdido cambiando entre procesos).
    
2. **Mejor rendimiento para procesos largos** → si las tareas suelen ser pesadas (por ejemplo, cálculos o simulaciones), terminan antes de ser interrumpidas.
    
3. **Más parecido a un sistema por lotes (batch)** → puede mejorar el throughput (cantidad de trabajo completado por unidad de tiempo) si las tareas no son interactivas.
    

#### ❌ **Desventajas:**

1. **Menor capacidad de respuesta** → los procesos cortos o interactivos (como los que esperan input del usuario) pueden tardar mucho en volver a ejecutar.
    
2. **Inequidad percibida** → un proceso que justo termine antes de que se acabe el quantum puede hacer esperar a los demás demasiado tiempo.
    
3. **Se pierde el espíritu del Round Robin** → con un quantum demasiado alto, se comporta casi como un planificador FCFS (_First Come, First Served_).
    

---
### ⚖️ **Resumen visual:**

|Quantum|Ventajas|Desventajas|Tipo de sistema recomendado|
|---|---|---|---|
|**Bajo**|Alta respuesta, justo con procesos cortos|Mucho cambio de contexto|Sistemas interactivos o en tiempo compartido|
|**Alto**|Menos overhead, más rendimiento para procesos largos|Menor interactividad|Sistemas batch o de procesamiento intensivo|
## 5. Una variante al algoritmo SJF es el algoritmo SJF apropiativo o SRTF (Shortest Remaining Time First):
### a.​ Realice el diagrama de Gantt para este algoritmo según el lote de trabajos del ejercicio 5
![[Pasted image 20251006162412.png]]

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    | 4   | 0   |
| 2    | 19  | 13  |
| 3    | 5   | 1   |
| 4    | 4   | 9   |
| 5    | 2   | 0   |
| PROM | 6,8 | 4,6 |

### b.​ ¿Nota alguna ventaja frente a otros algoritmos?

Esto significa que **si llega un nuevo proceso con un tiempo de ejecución restante menor** que el del proceso actual, **el CPU se le cede inmediatamente** a ese nuevo proceso.

---

### ✅ **Ventajas del SRTF**

1. **Tiempo de espera promedio mínimo**  
    Es el algoritmo óptimo en cuanto a **minimizar el tiempo de espera promedio**, porque siempre se elige el proceso que terminará más rápido.
    
    > Ejemplo: si llega un proceso corto mientras otro largo está ejecutando, el corto no queda “bloqueado” mucho tiempo.
    
2. **Mejor tiempo de respuesta para procesos cortos**  
    Los procesos pequeños o interactivos reciben atención casi inmediata, lo que mejora la **interactividad del sistema**.
    
3. **Uso eficiente del procesador**  
    El CPU está casi siempre ejecutando el proceso más conveniente (el que liberará antes el recurso), maximizando así la productividad global.
    

---

### ❌ **Desventajas (para contrastar)**

Aunque no lo pedís, vale la pena mencionarlas brevemente:

- Requiere **conocer o estimar la duración de los procesos**, lo cual no siempre es posible.
    
- Puede provocar **injusticia o inanición (starvation)**: procesos largos pueden esperar mucho si siguen llegando procesos cortos.
    
- Tiene **mayor sobrecarga** que el SJF no apropiativo, porque implica más decisiones de cambio de proceso.
    

---

### 🧩 **Resumen**

|Característica|SJF no apropiativo|**SRTF (apropiativo)**|
|---|---|---|
|Tipo|No interrumpe al proceso en ejecución|Puede interrumpir si llega uno más corto|
|Tiempo de espera promedio|Bajo|🔹 **Mínimo posible**|
|Tiempo de respuesta|Bueno|🔹 **Excelente para procesos cortos**|
|Sobrecarga|Menor|Mayor|
|Posible inanición|Moderada|Más probable|
## 6. Suponga que se agregan las siguientes prioridades al lote de procesos delejercicio 5, donde un menor número indica mayor prioridad:

| job | Prioridad | LLegada | Unidades de CPU |
| --- | --------- | ------- | --------------- |
| 1   | 3         | 0       | 4               |
| 2   | 4         | 2       | 6               |
| 3   | 2         | 3       | 4               |
| 4   | 1         | 6       | 5               |
| 5   | 2         | 8       | 2               |

### Apropiativo
![[Pasted image 20251007175016.png]]

| P    | TR   | TE  |
| ---- | ---- | --- |
| 1    | 15   | 11  |
| 2    | 19   | 13  |
| 3    | 9    | 5   |
| 4    | 5    | 0   |
| 5    | 6    | 4   |
| PROM | 10,8 | 6,6 |


### No Apropiativa
![[Pasted image 20251007175027.png]]

| P    | TR  | TE  |
| ---- | --- | --- |
| 1    |     |     |
| 2    |     |     |
| 3    |     |     |
| 4    |     |     |
| 5    |     |     |
| PROM |     |     |
### c.​ ¿Nota alguna ventaja frente a otros algoritmos? ¿Bajo qué circunstancias lo utilizaría y ante qué situaciones considera que la implementación de prioridades podría no ser de mayor relevancia?
**Ventajas frente a otros algoritmos:**

- Permite **dar preferencia a procesos críticos o más importantes**, algo que FCFS o SJF no consideran.
    
- Puede **mejorar el tiempo de respuesta de tareas urgentes**, garantizando que trabajos del sistema (por ejemplo, interrupciones o procesos interactivos) reciban CPU antes que los procesos de baja prioridad.
    
- En su versión **apropiativa**, puede reaccionar dinámicamente cuando llega un proceso de mayor prioridad, interrumpiendo otro en ejecución (útil en sistemas de tiempo real o interactivos).
    

**Cuándo lo usaría:**

- En **sistemas de tiempo real** o **multitarea interactiva**, donde algunas tareas deben ejecutarse antes que otras (por ejemplo, control de dispositivos, atención de eventos, o procesos del kernel).
    
- Cuando se necesita **controlar la política de planificación según la importancia o urgencia del proceso**.
    
- En entornos donde se puede **asignar prioridad según tipo de tarea o usuario** (por ejemplo, prioridad más alta a procesos del sistema y menor a procesos de usuario).
    

**Cuándo las prioridades podrían no ser relevantes o incluso problemáticas:**

- En sistemas donde **todos los procesos son equivalentes** o tienen **tiempos de CPU similares**, la prioridad no aporta beneficios reales frente a algoritmos más simples (como Round Robin o FCFS).
    
- Puede provocar **inanición (starvation)**: los procesos de baja prioridad podrían nunca ejecutarse si siguen llegando procesos de alta prioridad.
    
- Si las prioridades no están bien definidas o son asignadas arbitrariamente, el algoritmo pierde sentido y puede generar injusticia o ineficiencia.
    

---

👉 En resumen:

> El algoritmo por prioridades es ventajoso cuando hay distintos niveles de urgencia o criticidad en los procesos, pero pierde relevancia en sistemas homogéneos o donde se busca equidad.

## 7. Inanición
### 7.a. ¿Qué significa?

La **Inanición (Starvation)** ocurre cuando un proceso (o un hilo) está listo para ejecutarse, pero es **permanentemente postergado** e impedido de acceder a la CPU (u otro recurso vital) debido a un sesgo en el algoritmo de planificación.

En esencia, un proceso con baja prioridad puede esperar indefinidamente mientras procesos de mayor prioridad continúan llegando y acaparando la CPU. El proceso nunca muere de forma natural (por finalización), sino que "muere de hambre" al no recibir servicio.

---

### 7.b. ¿Cuál/es de los algoritmos vistos puede provocarla?

Los dos principales algoritmos que pueden causar inanición son:

1. **Planificación por Prioridades (Priority Scheduling):**
    
    - **Causa:** Un proceso de **baja prioridad** podría esperar indefinidamente si continuamente llegan o se crean nuevos procesos de **alta prioridad**.
        
2. **Shortest Job First (SJF) y Shortest Remaining Time First (SRTF):**
    
    - **Causa:** Un proceso con un **tiempo de ráfaga (burst time) muy largo** podría nunca ser seleccionado si hay un flujo constante de procesos con tiempos de ráfaga más cortos (o tiempos restantes más cortos).
        

---

### 7.c. ¿Existe alguna técnica que evite la inanición para el/los algoritmos mencionados en el inciso b?

Sí, la principal y más efectiva técnica para combatir la inanición, especialmente en la Planificación por Prioridades, es el **Envejecimiento (Aging)**. 👴

#### Envejecimiento (Aging)

- **Técnica:** Es un método que **incrementa gradualmente la prioridad** de los procesos que han estado esperando en la cola durante un tiempo excesivo.
    
- **Mecanismo:** Cuanto más tiempo pase un proceso sin recibir servicio, mayor será su prioridad.
    
- **Resultado:** Esto garantiza que, eventualmente, incluso el proceso con la prioridad inicial más baja alcanzará una prioridad lo suficientemente alta como para ser seleccionado y ejecutado, evitando así la inanición.
    

Esta técnica también puede aplicarse al algoritmo **SJF/SRTF** de forma implícita o explícita. Un proceso muy largo que espera mucho tiempo tiene su prioridad aumentada, asegurando que su gran tiempo de ráfaga se vea compensado por su elevada prioridad al final.
## 8. Agregarle al ejercicio 5 las siguientes operaciones
### FCFS

| job | LLegada | Unidades de CPU | I/0 (Recurso, instante, duración) | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  |
| --- | ------- | --------------- | --------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | 0       | 4               | (R1, 2, 1)                        | >1  | 2   | R1  |     |     |     | 3   | 4<  |     |     |     |     |
| 2   | 2       | 6               | (R2, 3, 1) (R2, 5, 2)             |     |     | >1  | 2   | 3   | R2  |     |     |     |     |     |     |
| 3   | 3       | 4               |                                   |     |     |     | >   |     |     |     |     | 1   | 2   | 3   | 4<  |
| 4   | 6       | 5               | (R3, 1, 2) (R3, 3, 1)             |     |     |     |     |     |     | >   |     |     |     |     |     |
| 5   | 8       | 2               |                                   |     |     |     |     |     |     |     |     | >   |     |     |     |
|     |         |                 |                                   |     |     |     |     |     |     |     |     |     |     |     |     |
|     | Queue   | 1               | ~~2~~                             | 3   | 4   | 5   |     |     |     |     |     |     |     |     |     |
|     | QueueR1 | 1               |                                   |     |     |     |     |     |     |     |     |     |     |     |     |
|     | QueueR2 |                 |                                   |     |     |     |     |     |     |     |     |     |     |     |     |
|     | QueueR3 |                 |                                   |     |     |     |     |     |     |     |     |     |     |     |     |
### FCFS 


---

## 19. Dados los siguientes programas en pseudo código que simulan la utilización de llamadas al sistema para crear procesos en Unix/linux, indicar qué mensajes se imprimirán en pantalla (sin importar el orden en el que saldrían)

```
a.​ Caso 1

printf(“hola”)
x = fork()
if x < 1 {
	execv(“ls”)
	printf(“mundo”)
	exit(0)
}
exit(0)
```
R: 
Hola!
imprime resultado de ls

```
b.​ Caso 2
	printf(“hola”)
	x = fork()
	if x < 1 {
		execv(“ps”)
		printf(“mundo”)
		exit(0)
	}
	execv(“ls”)
	printf(“fin”)
	exit(0)
```
R:
Hola
imprime resultado de ps (lista procesos)
imprime resultados de ls (lista directorios)
```
Caso 3
	printf(“Anda a rendir el Primer Parcial de Promo!”)
	newpid = fork()
	if newpid == 0 {
		printf(“Estoy comenzando el Examen”)
		execv(“ps”)
		printf(“Termine el Examen”)
	}
	printf(“¿Como te fue?”)
	exit(0)
	printf(“Ahora anda a descansar”)
```
R: 
Anda a rendir el primer parcial de promo!
Estoy comenzando el examen
resultado del comando ps
¿Cómo te fue?

---
## 20. Dado el siguiente programa en C, analice su objetivo sin necesidad de ejecutarlo.
```c
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main ( void ) {
	int c ;
	pid_t pid ;
	printf( " Comienzo . : \ n " ) ;
	for ( c = 0 ; c < 3 ; c++ ) {
		pid = fork ( ) ;
	}
	printf ( " Proceso \n " ) ;
	return 0 ;
}
```
RA: Este programa realiza 3 iteraciones, en cada una se ejecuta un fork, duplicando el proceso actual.
Por lo tanto el número de procesos se multiplica por 2 en cada iteración.
2 al cubo, quedan 8 líneas con la palabra proceso

RB: si, cada "proceso" proviene de un proceso diferente que llega a esa ejecución

---
## 21. Modifiquemos el programa anterior. Ahora además de un mensaje, vamos a añadir una variable y antes de finalizar vamos a mostrar el valor de la misma.
```c
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main ( void ) {
	int c ;
	pid_t pid ;
	int p = 0;
	printf( " Comienzo . : \ n " ) ;
	for ( c = 0 ; c < 3 ; c++ ) {
		pid = fork ( ) ;
	}
	p++;
	printf ( " Proceso %d\n ",p ) ;
	return 0 ;
}
```
RA: ¿Qué valores se imprimirán en consola?
El for crea 3 forks, al final se tienen 8 procesos.
Como la variable p se inicio antes del fork, todos heredan ese valor, entonces siempre imprime "Proceso 1".

RB: ¿Todas las líneas tendrán el mismo valor o algunas líneas tendrán valores distintos?
Todas las líneas tienen el mismo valor 1.

RC: ¿Cuál es el valor (o valores) que aparece?. Compile y ejecute el programa y pruebe si su respuesta es correcta.
Proceso1 X 8.

RD: ¿Realice modificaciones al programa, por ejemplo: modifique el valor del bucle for, cambie el lugar dónde se incrementa la variable p, y compruebe los nuevos resultados?
Si se coloca el incremento de p, dentro del bucle for, después del fork, ahora si se imprimiria proceso con su número correspondiente.

---
## 22. ¿Qué es la MMU y qué funciones cumple?
La **MMU** es la encargada de que cada proceso crea tener su propia memoria aislada y segura, traduciendo las direcciones que usa el programa en direcciones reales de la RAM y gestionando la protección y eficiencia del sistema de memoria. La MMU implementa mecanismos como paginación y segmentación!

---
## 23. ¿Qué representa el espacio de direcciones de un proceso?
El **espacio de direcciones** de un proceso representa **el conjunto de direcciones de memoria que ese proceso puede usar**.  
En otras palabras:

> Es **la visión que un proceso tiene de la memoria**, como si fuera toda suya, aunque en realidad el sistema operativo y la MMU la estén gestionando y aislando del resto.

---

### 🔍 **Detalles importantes**

1. **Cada proceso tiene su propio espacio de direcciones virtuales.**
    
    - Eso significa que dos procesos pueden usar, por ejemplo, la dirección `0x8048000`, pero en realidad apuntan a **lugares físicos distintos** en la RAM.
        
    - Esto lo logra la **MMU** mediante la **traducción de direcciones virtuales a físicas**.
        
2. **El espacio de direcciones es virtual.**
    
    - Los programas no trabajan con direcciones físicas reales, sino con **direcciones virtuales** que son mapeadas dinámicamente por el sistema operativo.
        
3. **Permite aislamiento y seguridad.**
    
    - Un proceso no puede acceder (salvo excepciones controladas) a la memoria de otro.
        
    - Así se evita que un error o ataque afecte a otros procesos o al kernel.
        

---

### 🧩 **Estructura típica del espacio de direcciones**

En un sistema típico (por ejemplo Linux de 32 bits), el espacio de direcciones de un proceso se organiza más o menos así:
```
+------------------------+  ← Direcciones altas
|   Kernel (SO)          |
+------------------------+
|   Pila (Stack)         | ← Crece hacia abajo
+------------------------+
|   Heap (malloc, new)   | ← Crece hacia arriba
+------------------------+
|   Datos estáticos      | ← Variables globales e inicializadas
+------------------------+
|   Código (Text)        | ← Instrucciones del programa
+------------------------+  ← Dirección 0

```
- **Código (text segment):** contiene las instrucciones del programa.
    
- **Datos (data segment):** variables globales y estáticas.
    
- **Heap:** memoria dinámica (malloc, new, etc.).
    
- **Stack:** pila de ejecución (funciones, variables locales).
### 🧭 **En resumen**

| Concepto   | Descripción                                                  |
| ---------- | ------------------------------------------------------------ |
| Definición | Conjunto de direcciones de memoria que un proceso puede usar |
| Tipo       | Virtual (no corresponde directamente a direcciones físicas)  |
| Propósito  | Aislar procesos y simplificar la gestión de memoria          |
| Estructura | Código, datos, heap, pila, y espacio del kernel              |

---
## 24. Explique y relacione los siguientes conceptos:
### Dirección lógica o virtual
- Es la **dirección de memoria que genera la CPU** cuando un programa se ejecuta.
    
- También se la llama **dirección virtual**, porque **no corresponde directamente a una posición física en la RAM**.
    
- Cada proceso trabaja con su propio conjunto de direcciones lógicas (su **espacio de direcciones**), lo que le da la **ilusión de tener toda la memoria para sí mismo**.

>[!tip] Ejemplo
> El proceso A accede a la dirección virtual `0x1000`.  
> El proceso B también puede usar `0x1000`, pero en realidad apuntan a diferentes zonas físicas de la RAM.

### Dirección física
- Es la **dirección real en la memoria RAM** donde se almacenan los datos o instrucciones.
    
- La memoria física es única para todo el sistema, y el sistema operativo se encarga de **asignar partes de ella a cada proceso**.
    
- Las direcciones físicas son las que la **MMU finalmente utiliza para acceder a la RAM**.
>[!tip] Ejemplo
>La dirección virtual `0x1000` del proceso A puede corresponder a la dirección física `0xABC000` en RAM.

---
## 25. 
En la técnica de Particiones Múltiples, la memoria es dividida en varias particiones y los espacios de direcciones de los procesos son ubicados en estas, siempre que el
tamaño del mismo sea menor o igual que el tamaño de la partición.
Al trabajar con particiones se pueden considerar 2 métodos (independientes
entre sí):
	​ Particiones Fijas
	​ Particiones Dinámicas

### a.​ Explique cómo trabajan estos 2 métodos. Cite diferencias, ventajas y desventajas.

#### Particiones Fijas
En el método de **particiones fijas**, la memoria principal se divide en varias particiones de **tamaños predefinidos y fijos** al iniciar el sistema operativo. Estas particiones no cambian de tamaño. A cada proceso se le asigna la primera partición disponible que sea lo suficientemente grande para alojarlo.

- **Ventajas:**
    
    - **Simplicidad:** Su implementación es relativamente sencilla.
        
    - **Baja sobrecarga:** No requiere mucha sobrecarga para su gestión.
        
- **Desventajas:**
    
    - **Fragmentación interna:** Un proceso pequeño puede ser asignado a una partición grande, dejando espacio sin usar dentro de esa partición. Esto desperdicia memoria.
        
    - **Limitación de tamaño:** Un proceso no puede ser más grande que la partición más grande disponible.
        
    - **Grado de multiprogramación limitado:** El número de procesos que pueden estar en memoria al mismo tiempo es igual al número de particiones.
#### Particiones Dinámicas
En el método de **particiones dinámicas**, la memoria **no se particiona de antemano**. Cuando un proceso necesita cargarse, se le asigna un bloque de memoria contiguo exactamente del tamaño que requiere. La partición se crea "sobre la marcha" y su tamaño es igual al tamaño del proceso.

- **Ventajas:**
    
    - **Sin fragmentación interna:** La memoria se asigna en el tamaño exacto del proceso, eliminando el desperdicio de memoria dentro de la partición.
        
    - **Uso eficiente de la memoria:** Se utiliza la cantidad de memoria que realmente se necesita.
        
- **Desventajas:**
    
    - **Fragmentación externa:** A medida que los procesos se cargan y se liberan, pueden quedar pequeños bloques de memoria libre dispersos. Aunque el espacio total libre sea suficiente para un nuevo proceso, puede que no haya un solo bloque contiguo lo suficientemente grande. Esto puede llevar a la necesidad de **compactación** de la memoria, que es un proceso costoso.
        
    - **Mayor complejidad:** La gestión de la memoria es más compleja, ya que el kernel debe llevar un registro de todos los bloques de memoria libres y ocupados.

### b.​ ¿Qué información debe disponer el Kernel para poder administrar la memoria principal con estos métodos?
Para administrar la memoria principal con estos métodos, el **kernel** del sistema operativo necesita mantener un registro de la siguiente información:

- **Información de las particiones (Fijas):** Para cada partición, el kernel debe saber su dirección de inicio y su tamaño.
    
- **Mapa de bits de la memoria (Dinámicas):** El kernel puede usar una estructura de datos como un mapa de bits para representar el estado de la memoria. Cada bit podría representar un bloque de memoria (por ejemplo, 1KB), indicando si está libre (0) u ocupado (1).
    
- **Lista de bloques libres y ocupados (Dinámicas):** Alternativamente, el kernel puede mantener dos listas enlazadas: una para los bloques de memoria libre y otra para los bloques ocupados. Cada entrada en la lista contendría la dirección de inicio del bloque y su tamaño.
    
- **Información de los procesos:** Para cada proceso, el kernel necesita conocer su **dirección de inicio en memoria física** y su **tamaño**. Esta información es crucial para la asignación y liberación de memoria.
### c.​ Realice un gráfico indicando cómo se realiza la transformación de direcciones lógicas a direcciones físicas.
La transformación de direcciones lógicas a físicas es un proceso fundamental en la gestión de memoria. Una **dirección lógica** es la que genera el procesador, mientras que una **dirección física** es la dirección real en la memoria principal. En el esquema de particiones, esta transformación se realiza de la siguiente manera:

1. **El procesador genera una dirección lógica.** Esta dirección consta de un **desplazamiento** (offset) desde el inicio del espacio de direcciones del proceso.
    
2. **El hardware de gestión de memoria (MMU)** toma esta dirección lógica.
    
3. **Se suma la dirección de inicio de la partición.** El kernel le proporciona a la MMU la dirección de inicio de la partición en la que se cargó el proceso.
    
4. **Se obtiene la dirección física.** Al sumar la dirección de inicio de la partición a la dirección lógica (desplazamiento), se obtiene la dirección física real en la memoria principal.
    

Esta operación se puede expresar con la siguiente fórmula:

**Dirección Física = Dirección de Inicio de la Partición + Dirección Lógica**

---
## 26. Al trabajar con particiones fijas:
Los tamaños de las mismas se pueden considerar :
- Particiones de igual tamaño
- Particiones dinámicas
Citar ventajas y desventajas entre las alternativas

### Particiones de igual tamaño
A cada proceso se le asigna una partición, siempre que su tamaño sea menor o igual.
Ventajas
- Simplicidad: la gestión es simple, el kernel solo necesita una lista o mapa de bits para saber que particiones están libres u ocupadas.
- Bajo overhead:: No se requiere una gran cantidad de cálculos para la asignación de memoria.
Desventajas
- Desperdicio de memoria: Si los procesos tienen tamaños muy variados, este método es ineficiente. Un proceso pequeño desperdiciaría una gran cantidad de espacio en la partición.
- Limitación de tamaño: Un proceso no puede ejecutarse si es más grande que el tamaño de la partición.
### Particiones de diferente tamaño
Se intenta de tener una variedad de tamaños para acomodar procesos pequeños, medianos y grandes.
Ventajas
- Menor desperdicio de memoria: Al tener particiones de diferentes tamaños, se puede asignar a un proceso una partición más adecuada a su tamaño, reduciendo la fragmentación interna. Un proceso pequeño puede ir a una partición pequeña, y uno grande a una grande
- Mayor flexibilidad: Permite que los procesos de diferentes tamaños coexistan en la memoria de manera más eficiente.
Desventajas
- Mayor complejidad: El kernel debe buscar la mejor de las particiones en una lista.
- Algoritmos de asignación: Se requieren algoritmos de asignación (como primer ajuste, mejor ajuste o peor ajuste) para decidir que partición usar.
---
## 27. Fragmentación
Ambos métodos de particiones presentan el problema de la fragmentación:
​ - Fragmentación Interna (Para el caso de Particiones Fijas)
​ - Fragmentación Externa (Para el caso de Particiones Dinámicas)

### a.​ Explique a qué hacen referencia estos 2 problemas

La **fragmentación interna** ocurre cuando a un proceso se le asigna un bloque de memoria más grande de lo que necesita. Esto es común en el método de **particiones fijas**. El espacio sobrante dentro del bloque asignado no puede ser utilizado por ningún otro proceso, lo que lleva a un desperdicio de memoria.

Por ejemplo, si un proceso necesita 25KB de memoria y se le asigna una partición de 30KB, los 5KB restantes son fragmentación interna. Esta memoria queda inutilizable hasta que el proceso termine.

La **fragmentación externa** se da cuando hay suficiente memoria total disponible para satisfacer una solicitud de un proceso, pero la memoria está dispersa en pequeños bloques no contiguos. Este problema es característico del método de **particiones dinámicas**, donde los procesos se cargan y descargan, dejando huecos de memoria libre.

Por ejemplo, si un proceso necesita 10KB y hay 5KB libres en una ubicación y otros 5KB en otra, el proceso no puede ser cargado porque la memoria no es contigua.

### b.​ El problema de la Fragmentación Externa es posible de subsanar. Explique una
El problema de la fragmentación externa se puede subsanar mediante una técnica llamada **compactación**. La compactación es el proceso de reorganizar la memoria para que todos los bloques de memoria libre se unan en un solo bloque contiguo.

La técnica funciona de la siguiente manera:

1. **El kernel detiene la ejecución de los procesos.**
    
2. **Mueve los bloques de memoria ocupados.** Todos los procesos que se encuentran en la memoria se desplazan a un extremo de la memoria principal (por lo general, el extremo inferior).
    
3. **Actualiza las direcciones de los procesos.** A medida que los procesos se mueven, sus direcciones de inicio en memoria física cambian. El kernel debe actualizar las tablas de direcciones de los procesos para que apunten a sus nuevas ubicaciones.
    
4. **Libera un bloque contiguo.** Una vez que todos los procesos se han movido, todo el espacio libre restante se consolida en un solo bloque grande, listo para ser asignado a un nuevo proceso.
    

Si bien la compactación es una solución efectiva para la fragmentación externa, es una operación costosa en términos de tiempo de CPU y puede causar una interrupción temporal en la ejecución de los procesos. Por esta razón, no se realiza con frecuencia, sino solo cuando la fragmentación externa alcanza un nivel crítico.

---
## 28. 
Analice y describa cómo funcionan las siguientes técnicas de asignación de
particiones: Best Fit, Worst Fit, First Fit y Next Fit. Tenga en cuenta que información
debe mantener el Kernel. Indique, para los métodos de particiones dinámicas y
fijas, con cuál técnica se obtienen mejores resultados y justifique.

### Técnicas de Asignación de Particiones

Estas técnicas se utilizan para decidir qué partición de memoria libre se asigna a un nuevo proceso. Para poder aplicar estos algoritmos, el **kernel** debe mantener una **lista enlazada** de todas las particiones de memoria, indicando si están libres u ocupadas, y su dirección de inicio y tamaño.

#### First Fit (Primer Ajuste)

- **Funcionamiento:** El kernel busca en la lista de particiones desde el principio y asigna al proceso la **primera partición libre** que sea lo suficientemente grande para contenerlo.
    
- **Información del Kernel:** Debe tener la lista completa de particiones y un puntero a la última partición asignada para empezar la búsqueda en el siguiente punto.
    
- **Análisis:** Es la técnica más simple y rápida, ya que no necesita buscar la mejor opción. Sin embargo, puede llevar a una fragmentación externa significativa, especialmente si los primeros bloques son pequeños, dejando los grandes para procesos que podrían no necesitarlos.
    

---

### Next Fit (Siguiente Ajuste)

- **Funcionamiento:** Similar a First Fit, pero la búsqueda de la siguiente partición libre comienza **desde donde terminó la última búsqueda**, no desde el inicio de la lista.
    
- **Información del Kernel:** Debe mantener un puntero que apunte a la última partición asignada.
    
- **Análisis:** Es un poco más rápido que First Fit en promedio, ya que distribuye la búsqueda por toda la memoria, pero puede generar una fragmentación externa aún más dispersa.
    

---

### Best Fit (Mejor Ajuste)

- **Funcionamiento:** El kernel examina toda la lista de particiones libres y asigna al proceso la partición que sea **la más pequeña pero aún lo suficientemente grande** para contenerlo. El objetivo es minimizar el espacio sobrante.
    
- **Información del Kernel:** Debe recorrer la lista completa de particiones libres para encontrar la mejor opción.
    
- **Análisis:** Minimiza la fragmentación interna al no desperdiciar grandes cantidades de espacio. Sin embargo, puede dejar muchos bloques de memoria muy pequeños (fragmentación externa), que son difíciles de usar para futuros procesos. Es más lento que First Fit o Next Fit porque requiere una búsqueda exhaustiva.
    

---

### Worst Fit (Peor Ajuste)

- **Funcionamiento:** El kernel busca la partición **más grande** de la lista y se la asigna al proceso. La lógica es que el espacio sobrante de una partición muy grande será lo suficientemente grande para ser útil para otros procesos pequeños.
    
- **Información del Kernel:** Requiere una búsqueda exhaustiva similar a Best Fit para encontrar la partición más grande.
    
- **Análisis:** Intenta evitar la acumulación de fragmentos muy pequeños y inútiles. Sin embargo, al usar el bloque más grande, puede resultar en que un proceso grande que llegue después no tenga espacio suficiente.
    

---
### Comparativa y Justificación

### Particiones Fijas

En las **particiones fijas**, el mejor método es **Best Fit**. Dado que las particiones tienen un tamaño fijo, el principal problema es la **fragmentación interna**. Al elegir la partición más ajustada posible (Best Fit), se minimiza el espacio desperdiciado dentro de la partición asignada. Los otros métodos, como First Fit, podrían asignar un proceso pequeño a una partición muy grande, aumentando la fragmentación interna.

### Particiones Dinámicas

En las **particiones dinámicas**, la principal preocupación es la **fragmentación externa**. Los métodos que funcionan mejor son **First Fit y Next Fit** en términos de rendimiento general y balance. Aunque Best Fit minimiza la fragmentación interna (lo cual no es un problema en particiones dinámicas), su tendencia a dejar pequeños huecos inútiles (fragmentación externa) lo hace menos deseable. Los métodos First Fit y Next Fit son más rápidos y, aunque contribuyen a la fragmentación externa, lo hacen de una manera que puede ser más manejable.

---
## 29. Segmentación 
a.​ Explique cómo trabaja este método de asignación de memoria.
b.​ ¿Qué estructuras son necesarias en el Kernel para poder ejecutarse sobre un
Hardware que utiliza segmentación?
c.​ Explique, utilizando gráficos, cómo son resueltas las direcciones lógicas a
físicas.
d.​ En este esquema: ¿se puede producir fragmentación (interna y/o externa)?
e.​ De las técnicas enumeradas en el ejercicio 29 ¿Cuál se ajusta mejor para la
asignación de memoria principal?

### a. Funcionamiento del Método

La **segmentación** es un método de gestión de memoria que divide el espacio de direcciones de un proceso en bloques lógicos de tamaño variable llamados **segmentos**. Cada segmento corresponde a una parte lógica del programa (por ejemplo, el código, la pila, los datos, etc.). Los segmentos no necesitan ser contiguos en la memoria física.

### b. Estructuras del Kernel

Para utilizar segmentación, el Kernel debe tener una **tabla de segmentos** para cada proceso. Cada entrada en esta tabla contiene:

- **Dirección Base:** La dirección física de inicio del segmento en la memoria principal.
    
- **Límite (o Longitud):** El tamaño del segmento.
    

### c. Resolución de Direcciones Lógicas a Físicas

La dirección lógica en un sistema segmentado se compone de dos partes:

- **Número de Segmento:** Identifica a qué segmento pertenece la dirección.
    
- **Desplazamiento (Offset):** Indica la posición dentro de ese segmento.
    

La **Unidad de Gestión de Memoria (MMU)** realiza la traducción. . El proceso es el siguiente:

1. La MMU recibe una dirección lógica (segmento, desplazamiento).
    
2. Utiliza el **número de segmento** para buscar la entrada correspondiente en la **tabla de segmentos**.
    
3. Comprueba que el **desplazamiento** no supere el **límite** del segmento para evitar accesos fuera de los límites. Si es mayor, se genera un error.
    
4. Suma la **dirección base** del segmento (obtenida de la tabla) al **desplazamiento** para obtener la **dirección física** real en la memoria.
    

### d. Fragmentación

- **Fragmentación Interna:** No se produce. Los segmentos se asignan con el tamaño exacto que el proceso requiere, sin dejar espacio no utilizado dentro de ellos.
    
- **Fragmentación Externa:** **Sí se produce**. A medida que los procesos (o segmentos) se cargan y descargan, la memoria se llena de bloques libres de diferentes tamaños dispersos, lo que lleva a la fragmentación externa, similar a las particiones dinámicas.
    

### e. Técnica de Asignación

Para la asignación de memoria principal en la segmentación, las técnicas del Ejercicio 28 son aplicables. **First Fit** y **Next Fit** son las que mejor se ajustan. Como la segmentación presenta **fragmentación externa**, estas técnicas son eficientes y rápidas para encontrar el primer segmento de memoria libre lo suficientemente grande. Aunque Best Fit podría parecer ideal, su lentitud y la creación de pequeños huecos de memoria lo hacen menos deseable en un sistema de segmentación donde la fragmentación externa es el principal problema.

---
## 30.
​Dado un esquema de segmentación donde cada dirección hace referencia a 1 byte y la siguiente tabla de segmentos de un proceso, traduzca, de corresponder, las direcciones lógicas indicadas a direcciones físicas. La Dirección lógica está representada por: Segmento: deplazamiento


| Segmento | Dir. Base | Tamaño |
| -------- | --------- | ------ |
| 0        | 102       | 12500  |
| 1        | 28699     | 24300  |
| 2        | 68010     | 15855  |
| 3        | 80001     | 400    |
### i. 0000:9001
base + desplazamiento = Direccion física
102 + 9001 = 9103
### ii. 0001:24301
28699 + 24301 = 53000 El desplazamiento cae fuera del espacio de direcciones, operación inválida.
### iii. 0002:5678
68010 + 5678 = 73688
### iv. 0001:18976
28699 + 18976 = 47675
### v. 0003:0
80001 + 0 = 80001  

---
## 31. Paginación
### a.​ Explique cómo trabaja este método de asignación de memoria.
La **paginación** es un método de asignación de memoria no contigua que permite a los procesos residir en fragmentos físicos de memoria no adyacentes. El objetivo principal de la paginación es **resolver el problema de la fragmentación externa**.

El sistema divide la memoria física en bloques de tamaño fijo llamados **marcos de página** (`frames`). Al mismo tiempo, el sistema divide la memoria lógica de cada proceso en bloques del mismo tamaño llamados **páginas** (`pages`).

Cuando un proceso necesita ejecutarse, el sistema operativo le asigna marcos de página disponibles en la memoria física para almacenar sus páginas lógicas. Los marcos de página pueden estar dispersos por toda la memoria física sin necesidad de ser contiguos. El mapeo entre las páginas lógicas y los marcos de página físicos lo realiza el hardware con ayuda del sistema operativo.

### b.​ ¿Qué estructuras son necesarias en el Kernel para poder ejecutarse sobre un Hardware que utiliza paginación ?
Para que un sistema operativo se ejecute sobre un hardware que utiliza paginación, el Kernel necesita al menos las siguientes estructuras de datos principales:

- **Tabla de páginas (`Page Table`):** Es una estructura de datos fundamental, generalmente almacenada en la memoria principal, que contiene la correspondencia entre las páginas lógicas de un proceso y los marcos de página físicos en la memoria. Cada proceso en ejecución tiene su propia tabla de páginas.
    
- **Registro de tabla de páginas (`Page Table Base Register` o `PTBR`):** Este registro de hardware, ubicado en la **unidad de gestión de memoria** (`MMU`), apunta a la dirección de inicio de la tabla de páginas del proceso en ejecución.

### c.​ Explique, utilizando gráficos, cómo son resueltas las direcciones lógicas en físicas.
La resolución de una dirección lógica a una física en un esquema de paginación se realiza en dos pasos:

1. **División de la dirección lógica:** La dirección lógica se divide en dos partes por el hardware:
    
    - **Número de página (`p`):** La parte superior de la dirección, que se utiliza como índice para la tabla de páginas.
        
    - **Desplazamiento (`d`):** La parte inferior de la dirección, que indica la posición dentro de la página.
        
2. **Traducción de la dirección:** La **Unidad de Gestión de Memoria (`MMU`)** utiliza el **número de página** para buscar en la **tabla de páginas del proceso** (cuya dirección está en el PTBR). El valor en la entrada de la tabla de páginas correspondiente a `p` contiene el **número de marco de página** físico (`f`). La dirección física se construye concatenando el número de marco de página (`f`) y el desplazamiento (`d`).
    

Direccion logica: (p,d)

Direccioˊn fısica: (f,d)

Donde f es el número de marco de página que se encuentra en la entrada p de la tabla de páginas.
### d.​ En este esquema: ¿se puede producir fragmentación (interna y/o externa)?
En este esquema, se puede producir **fragmentación interna**, pero **no fragmentación externa**.

- **Fragmentación interna:** Ocurre si el tamaño de un proceso no es un múltiplo exacto del tamaño de la página. La última página del proceso puede no llenarse por completo, dejando un espacio no utilizado dentro de un marco de página. Este espacio es memoria desperdiciada que no puede ser asignada a otro proceso.
    
- **Fragmentación externa:** Es la memoria libre que está dispersa en pequeños bloques entre bloques de memoria asignados. La paginación evita este problema al permitir que los procesos residan en marcos de página no contiguos, eliminando la necesidad de buscar un bloque de memoria contiguo lo suficientemente grande para todo el proceso.
---
## 32. Suponga un sistema donde la memoria es administrada mediante la técnica de paginación, y donde:
- El tamaño de la página es de 512 bytes
- Cada dirección de memoria referencia 1 byte.
- Se tiene una memoria principal de 10240 bytes (10 KiB) y los marcos enumeran desde 0 y comienzan en la dirección física 0.
Suponga además un proceso P1 con un tamaño lógico de 2000 bytes y con la siguiente tabla de páginas:

| Página | Marco |
| ------ | ----- |
| 0      | 3     |
| 1      | 5     |
| 2      | 2     |
| 3      | 6     |
### a. Realice los gráficos necesarios (de la memoria principal, del espacio de direcciones del proceso, de tabla de páginas y de la tabla de marcos) en el que refleje el estado descripto.
num marco * tam pagina = base
num marco sig * tam pag - 1 = límite

| Marco | Inicio-Fin |
| ----- | ---------- |
| 0     | 0-511      |
| 1     | 512-1023   |
| 2     | 1024-1535  |
| 3     | 1536-2047  |
| 4     | 2048-2559  |
| 5     | 2560-3071  |
| 6     | 3072-3583  |
### b. Indicar si las siguientes direcciones lógicas corresponden al espacio lógico del proceso P1 y en caso afirmativo indicar la dirección física a la que corresponden.
>[!tip] Div con la calculadora
> El resto entero de la división
> Ejemplo : 15 / 4 = 3.75 
> Res = 3

>[!tip] Mod con calculadora
>**Fórmula:** a(modb)= a − (parte entera de (a÷b)) × b
>**Ejemplo:** ¿Cuánto es 15(mod4)?
>1. Calcula 15 / 4 = 3.75
>2. La parte entera es 3
>3. Multiplicar esa parte por el divisor: 3x4 = 12
>4. Restar el resultado del dividendo : 15 - 12 = 3
>5. Modulo es 3.

>[!danger] De lógica a física
>Página = DL div Tamaño página
>Desplazamiento = DL mod Tamaño página
>DF = (marco X tam página ) + desplazamiento
#### i. 35
35 div 512 = 0 (página 0, corresponde al marco 3)
35 mod 512 = 35 desplazamiento
Dirección física = marco X tam pag) + desplazamiento
1536 + 35 = 1571 válida porque está dentro del rango!
#### ii. 512
512 div 512 = 1 ( página 1, marco 5)
512 mod 512 = 0 desplazamiento
Dirección física = 2560 + 0 = 2560 válida está dentro del rango
#### iii. 2051
2051 div 512 = 4 (página 4, no está en la tabla del proceso, dirección inválida)
#### iv. 0
0 div 512 = 0 (página 0, marco 3)
0 mod 512 = 0 desplazamiento 
Dirección física = 1536 (dentro de rango dirección válida)
#### v. 1325
1325 div 512 = 2 (página 2, corresponde al marco 2)
1325 mod 512 = 301 desplazamiento
Dirección física = 1024 + 301 = 1325 (dentro del rango dirección válida)
#### vi. 602
602 div 512 = 1 (página 1, corresponde marco 5)
605 mod 512 = 93 desplazamiento 
### c. Indicar en caso de ser posible, las direcciones lógicas del proceso p1 que se corresponden a las siguientes direcciones físicas
>[!danger] de fisicas a lógicas
>marco = DF / Tam pag
>desplazamiento = Df mod tam Pag
>DL = (página x tamaño de página) + desplazamiento
#### i. 509
509 div 512 = 0 (marco 0 no se corresponde con ninguna página)
#### ii.1500
1500 div 512 = 2 (marco 2 corresponde con página 2)
1500 mod 512 = 476 desplazamiento
Dirección lógica = 2 * 512 + 476  = 1500 
#### iii.0
0 div 512 = 0 (marco 0 no se corresponde con ninguna página)
#### iv. 3215
3215 div 512 = 6 (marco 6 se corresponde con página 3)
3215 mod 512 = 143 desplazamiento
Dirección Lógica = 3 * 512 +143 = 1679 
#### v. 1024
1024 div 512 = 2 (marco 2 se corresponde con página 2)
1024 mod 512 = 0 desplazamiento
Dirección lógica = 2 * 512 + 0 = 1024
#### vi. 2000
2000 div 512 = 3 (marco 3, se corresponde a pagina 0)
2000 mod 512 = 464 desplazamiento
Dirección lógica = 0 * 521 + 464 = 464