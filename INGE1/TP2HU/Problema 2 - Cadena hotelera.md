**ID Reservar Hospedaje**
**Título** : Como usuario quiero reservar un hospedaje para asegurar mi alojamiento en un hotel
**Reglas de negocio** :
- La fecha de ingreso debe estar dentro de los 90 días a partir de la fecha actual y el egreso
- La duración máxima de una estadía es de 15 días
--- 
**Criterios de aceptación** (Reservar hospedaje)
**Escenario 1: Reserva exitosa**
**Dado** una fecha de ingreso dentro de los 90 días y una estadía de hasta 15 días,
**Cuando** el usuario ingresa una fecha y confirma la reserva,
**Entonces** el sistema envía un correo electrónico con un código de reserva y un enlace para continuar con el pago.

---
**Escenario 2: Reserva fallida por rango de fecha excedido**
**Dado** una fecha de ingreso que está fuera del rango de los 90 días a partir de la fecha actual,
**Cuando** el usuario ingresa fechas y confirma la reserva,
**Entonces** el sistema informa que no se puede realizar por la fecha de ingreso.

---
**Escenario 3: Reserva fallida por duración de estadía**
**Dado** una fecha de ingreso dentro de los 90 días y una estadía de más de 15 días,
**Cuando** el usuario ingresa las fechas y confirma la reserva,
**Entonces** el sistema informa que las reservas no pueden durar más de 15 días.

---
---
**ID Realizar check in**
**Título** : Como usuario quiero realizar el check in  para recibir mi asignación de habitación.
**Reglas de negocio** :
- El check in debe realizarse entre las 10:00 am y las 23:59 pm
---
**Criterios de aceptación** (Realizar check in)
**Escenario 1: Check in exitoso**
**Dado** el horario actual está dentro del rango permitido (10:00-23:59) y un código de reserva válido para la fecha actual ,
**Cuando** el usuario ingresa el código y confirma el check in
**Entonces** el sistema informa la habitación asignada y envía un mensaje a un conserje del hotel para que guíe al usuario a la habitación y otro mensaje a los botones para que se ocupen de las valijas.

---
**Escenario 2: Check in fallido por código inválido** 
**Dado** el horario actual dentro del rango permitido y un código de reserva no válido,
**Cuando** el usuario ingresa el código de reserva,
**Entonces** el sistema informa que el código es inválido.

---
**Escenario 3: Reserva fallida por hora fuera de rango**
**Dado** el horario actual fuera del rango permitido y un código de reserva válido,
**Cuando** el usuario ingresa el código de reserva y se intenta realizar el check in en una hora fuera del rango,
**Entonces** el sistema informa que todavía no se encuentra habilitado los ingresos al hotel.

---
---
**ID** Realizar check out
**Título** : Como conserje quiero realizar el check out para liberar una habitación y dejarla disponible.
**Reglas de negocio** :
- Solo se puede realizar el check out de las habitaciones sin gastos
---
**Criterios de aceptación** (Realizar check out)
**Escenario 1:** Check out realizado con exito
**Dado** una habitación que no realizo ningún gasto adicional,
**Cuando** el conserje ingresa el número de habitación y realiza el checkout,
**Entonces** el sistema libera la habitación y envía un mensaje a los empleados para que se limpie la habitación.

---
**Escenario 2:** Check out fallido por gastos adicionales registrados
**Dado** una habitación con gastos pendientes,
**Cuando** el conserje ingresa el número de habitación y solicita check out,
**Entonces** el sistema informa que no se puede realizar el check out hasta que se abonen los gastos.