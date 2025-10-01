
---
**ID Reservar mueble**
**Título:** Como usuario quiero realizar una reserva para poder alquilar.
**Reglas de Negocio:** 
- Abonar el 20% del total del alquiler
- Solo con tarjeta de crédito
---
**Criterios de Aceptación(Reservar alquiler)**
**Escenario 1: Reserva Exitosa**
**Dado** que los tres muebles se encuentran disponibles para la fecha que ingreso el usuario y las condiciones de pago son exitosas
**cuando** el usuario selecciona ¨armario¨,¨mesa de luz¨ y ¨cama¨, la fecha DD-MM-YY, lugar del evento ¨x¨, cantidad de días ¨k¨
**Entonces** el sistema registra la reserva, saca de disponibilidad los muebles y le otorga un número de reserva al cliente.

**Escenario 2: Reserva fallida por no disponer de un mueble**
**Dado** que ¨armario¨ o ¨mesa de luz¨ o ¨cama¨ no se encuentra disponible y las condiciones del pago sean satisfactorias
**cuando**
**entonces**

**Escenario 3**



--- 
--- 
**ID** Cargar mueble
**Título** Como encargado quiero cargar un mueble al sistema para poder alquilarlo
**Reglas de negocio:**
- No debe haber códigos repetidos
---
**Criterios de aceptación (Cargar mueble)**
**Escenario 1: Carga exitosa** 
**Dado** que el código de inventario es único
**Cuando** se ingresa código de inventario ¨ooo¨, tipo de mueble ¨mesa¨ , fecha creación ¨dd-mm-yyyy¨, fecha de último mantenimiento ¨dd-mm-yyyy¨, estado ¨libre" y precio ¨500¨
**Entonces** se realiza la carga en el sistema