**ID** Asociar socio
**Título** : Como alumno deseo asociarme a la biblioteca para poder tomar prestamos de libros.
**Reglas de negocio** :
- Es necesario tener dni para asociarse.
---
**Criterios de aceptación** (Asociarse)
**Escenario 1:** Asociación exitosa
**Dado** que el alumno presenta su dni, 
**Cuando** la bibliotecaria registra los datos del alumno,
**Entonces** el sistema le otorga un carnet con su correspondiente número de socio

---
**Escenario 2:** Asociación fallida por dni registrado
**Dado** que el alumno presenta su dni,
**Cuando** la biblotecaria registra el dni ya existente en el sistema
**Entonces** se informa que el dni ya está asociado a un socio y se rechaza la operación.

---
---
**ID** Solicitar préstamo
**Título** : Como socio quiero solicitar un préstamo de un libro para poder leerlo.
**Reglas de negocio** :
- Los libros deben estar en buen estado,
- Un socio está habilitado si no tiene más de 3 préstamos vigentes y no tengan prestamos vencidos 
---
**Criterios de aceptación** ()
**Escenario 1:** Préstamo exitoso
**Dado** un socio que está habilitado, tiene menos de 3 prestamos vigentes y el libro está en buen estado,
**Cuando** el socio intenta solicitar un libro,
**Entonces** el sistema registra el préstamo y el libro queda marcado como prestado.

---
**Escenario 2:** Préstamo fallido por límite de libros
**Dado** un socio que está habilitado, tiene 3 prestamos vigentes y el libro está en buen estado,
**Cuando** el socio intenta solicitar un libro,
**Entonces** el sistema informa que se ha excedido la cantidad  máxima de prestamos vigentes.

---
**Escenario 3:** Préstamo fallido por libro en mal estado
**Dado** que el ejemplar solicitado se encuentra **deteriorado**, 
**Cuando** la bibliotecaria intenta registrar el préstamo de ese ejemplar,
**Entonces** el sistema rechaza la operación informando que el libro no está en condiciones

---
**Escenario 4:** Préstamo fallido por vencimiento de préstamo
**Dado** que el socio posee un préstamo que venció el plazo, 
**Cuando** el socio intenta solicitar el libro,
**Entonces** el sistema rechaza la solicitud e informa el vencimiento de un préstamo anterior

---
---
**ID** Retornar libro 
**Título** : Como usuario quiero retornar un libro y terminar el préstamo.
**Reglas de negocio** :
- Si el préstamo se encuentra vencido se suspende al socio por 15 días 
---
**Criterios de aceptación** (Retornar libro)
**Escenario 1:** Retorno exitoso
**Dado** que el socio devuelve un libro cuyo préstamo **no se encuentra vencido**, **Cuando** la bibliotecaria registra la devolución, **Entonces** el sistema registra el libro como disponible y el socio mantiene su estado de habilitado.

---
**Escenario 2:** Retorno con préstamo vencido
**Dado** que el socio devuelve un libro cuyo préstamo **se encuentra vencido**, **Cuando** la bibliotecaria registra la devolución, **Entonces** el sistema registra el libro como disponible y el sistema **suspende al socio por 15 días**
