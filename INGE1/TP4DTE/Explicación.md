---

---
---
## Diagramas de Transición de Estados
Se utilizan en sistemas de tiempo real, modelado de procesos y sistemas de control. Nos permite modelar el comportamiento de un sistema en función del tiempo.

---
## Elementos de un DTE
### Estado
Se representa como un rectángulo, identifica un periodo de tiempo (no instantáneo) de un objeto/entidad en el cual el sistema está esperando alguna operación o realizando alguna acción.
>[!tip] Ejemplos
> Funcionando, Configurando Temperatura, Configurando Tiempo
### Transición
Se representan como una flecha, con dirección u
única. Tienen 3 partes.
	Evento(Condición)/Acción
"--------------------------------->
- Evento: suceso que provoca que el sistema cambie de estado OBLIGATORIO!
- Condición: **impide** que el sistema cambie de estado al darse un evento OPCIONAL (puede haber transiciones sin condiciones)
- Acción: una o más tareas instantáneas que hace el sistema durante la transición de un estado al otro OPCIONAL (puede haber transiciones sin acciones)
### Estado inicial 
Estado inicial:  Único = Circulo relleno
Estado final: Varios = Circulo con punto

---
## Convenciones
### Los nombres de los estados ..
deben ser verbos en gerundio (ando-endo: ingresando, esperando)
### Eventos
Manifiestan la ocurrencia de un estímulo que conlleva la salida del estado (no confundir con una acción)
Tiene forma impersonal : Se presionó tecla
### Condición
Es una condición lógica que puede evaluar el sistema
Ej: tecla es "Enter"
### Acción
Verbo en infinitivo con sustantivo en función del sistema
(no confundir con acciones del usuario, como "presionar tecla")impide

---
## Cosas a tener en cuenta
El modelado se realiza desde el punto de vista del sistema y NO desde el punto de vista del usuario.
Por ejemplo, "presionar tecla" es una acción que no maneja el sistema, es parte del usuario. Desde el sistema, las acciones de un usuario se modelan como eventos:
ej: "Se presionó una tecla"
>[!danger] Importante
>condiciones y acciones se redactan en lenguaje natural. En vez de escribir "intentos++" usar "Incrementar intentos"

## Pasos
Breves pasos para la construcción de un DTE
1. ​ Identificar todos los estados del sistema y representarlos como cajas. Los nombres de los estados se escriben en gerundio.
2. Desde el estado inicial (único), comenzar a identificar los cambios del sistema que lo llevan de un estado a otro y representarlos con flechas (transiciones) que van desde el estado origen al estado destino.
3. Analizar, para cada transición, el evento, condiciones y las acciones para pasar de un estado a otro.
4. Verificación de Consistencia: una vez dibujado el DTE debemos verificar que se cumplan las siguientes condiciones.
- Se han definido todos los estados.
- Se pueden alcanzar todos los estados.
- Se puede salir de todos los estados.
- En cada estado, el sistema responde a todas las condiciones posibles (Normales y Anormales). No debería haber transiciones recurrentes (mismo estado origen y destino) sin acciones.