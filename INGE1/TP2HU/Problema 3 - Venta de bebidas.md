**ID** Registrar persona
**Título** : como usuario me quiero registrar con mis datos para poder comprar bebidas.
**Reglas de negocio** :
- El usuario que se desee registrar debe  ser mayor de edad
- El correo electrónico debe ser único para ser utilizado como nombre de usuario
---
**Criterios de aceptación** (Registrarse en el sistema)
**Escenario 1:** Registro exitoso
**Dado** un usuario con mayoría de edad y un correo no registrado,
**Cuando** ingresa nombre, apellido, edad, correo electrónico, y presiona registrarse, 
**Entonces** el sistema genera una contraseña y se envía al correo electrónico ingresado finalizando el registro

---
**Escenario 2:** Registro fallido por ser menor de edad
**Dado** una persona que no es mayor de edad (menor de 18 años)
**Cuando** intenta ingresar nombre, apellido, edad menor a 18 años y correo electrónico,
**Entonces** el sistema muestra en pantalla el texto de la ley que impide la venta a menores de 18 años.

---
**Escenario 3:** Registro fallido por correo existente
**Dado** que el correo ya está registrado
**Cuando** la persona intenta registrarse,
**Entonces** el sistema informa que el correo ya se encuentra registrado

---
---
**ID** Inicio de sesión
**Título** : Como usuario me quiero identificar para poder acceder al catálogo de bebidas y poder comprar.
**Reglas de negocio** :
- N/A
---
**Criterios de aceptación** (Inicio de sesión)
**Escenario 1:** Inicio de sesión exitoso
**Dado** un correo electrónico registrado y una contraseña válida,
**Cuando** el usuario ingresa el correo como usuario y la contraseña,
**Entonces** el sistema registra la sesión y se le otorga al usuario las acciones permitidas.

---
**Escenario 2:** Inicio de sesión fallido
**Dado** un correo electrónico o contraseña inválida, 
**Cuando** el usuario ingresa el correo como nombre de usuario y la contraseña,
**Entonces** el sistema notifica la discrepancia y solicita reintentar.

---
---
**ID** Comprar bebidas
**Título** : Como usuario quiero comprar bebidas y recibir el descuento correspondiente para realizar y finalizar mi compra.
**Reglas de negocio** :
- Los usuarios premium reciben un 20% de descuento al total
- Cualquier usuario con un carrito con monto superior a los $4500 recibe un 10% de descuento 
---
**Criterios de aceptación** (Comprar bebidas)
**Escenario 1:** Compra con descuento premium
**Dado** un usuario que inicia sesión,  figura como premium
**Cuando** se seleccionan los productos y procede al pago
**Entonces** se le aplica un descuento del 20% al monto total, informandolo en pantalla.

---
**Escenario 2:** Compra con descuento por monto total
**Dado** que el usuario inicia sesión, no es premium,
**Cuando** selecciona los productos y el total supera los $4500
**Entonces** se le aplica un descuento del 10% al total y se informa en pantalla.

---
**Escenario 3:** Compra con ambos descuentos
**Dado** que el usuario inicia sesión, es  premium, y la compra total es de $5000
**Cuando** selecciona los productos y procede con el pago
**Entonces** se le aplican ambos descuentos al total (30%) y se informa en pantalla.

---
**Escenario 4:** Compra sin descuentos 
**Dado** que el usuario inicia sesión, no es premium,
**Cuando** selecciona los productos, el total es inferior a los $4500 y procede con el pago,
**Entonces** el sistema informa el total, sin aplicar ningún descuento.