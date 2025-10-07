A partir de las tablas, como operamos con ellas mediante operaciones simples, utilizando un lenguaje teórico para la manipulación de datos.
## Selección
produce una tabla que contiene solo las tuplas de T que satisfacen el predicado p.
- Insertar ejemplo pp
## Proyección 
produce una **tabla** con un subconjunto de atributos de T eliminando las tuplas duplicadas.
>[!note] ejemplo
>me traigo solo la columna nombres de una tabla 
- Insertar ejemplo pp
## Unión
Produce una tabla que contiene todas las tuplas de T1 + T2, eliminando las duplicadas.
>[!warning] Ambas tablas deben ser compatibles
>Sus esquemas deben ser equivalentes en cantidad, posición y dominio de los atributos, aunque sus nombres si pueden ser distintos.

## Intersección
Produce una tabla que contiene todas las tuplas que se encuentran tanto enT1 como en T2. Ambas deben tener esquemas compatibles.
## Diferencia
Produce una tabla que contiene todas las tuplas de T1 que no se encuentran en T2. Ambas deben tener esquemas compatibles.
## Producto cartesiano
Produce una tabla concatenando cada tupla de T1 con todas las tuplas de T2
Se suele utilizar en conjunto con otras operaciones para retener la información que nos importa
## Producto natural
"Producto cartesiano seguido de una selección"
Produce una tabla concatenando tuplas de ambas tablas que tengan valores iguales en atributos con igual nombre. Se elimina uno de los ejemplares de cada atributo común.
## Renombre 
## Asignación
Vuelca A los resultados de consulta. Luego puedo utilizar A.