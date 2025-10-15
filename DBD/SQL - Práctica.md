DML -> lo que vemos en la práctica
## Select

```sql
Ejemplo:
	Alumno = (dni,nombre,apellido)
	SELECT nombre
	FROM alumno
	
	SELECT DISTINCT nombre
	FROM alumno //elimina tuplas repetidas
```
>[!tip] Operadores
>Se pueden añadir operadores para filtrar con más precisión, como > ,<, >=, BETWEEN, LIKE
## Operador Like 
sirve para trabajar con cadenas de string, es muy poderoso.
```sql
SELECT nombre, apellido
FROM alumno
WHERE (nombre LIKE '___') // devuelve los que tienen 3 letras, --- es x cáracter

SELECT nombre, apellido
FROM alumno
WHERE (apellido LIKE '%or%') // los que contengan 'or'
```
## Operador IS NULL
Me dice si un atributo tiene valor nulo, existe su negación
```sql
SELECT nombre, apellido
FROM alumno
WHERE (nombre IS NOT NULL)
```
## Producto cartesiano y renombres
Se utilizan  dos tablas separadas por comas
```sql
#Producto
SELECT *
FROM alumno, localidad
---
#RENOMBRE
SELECT a.nombre as 'Nombre alumno', l.nombre as 'Nombre localidad'
FROM alumno a,localidad l
```
>[!danger] NO SE PUEDE USAR
un renombre que hice en el select en la consulta, porque todavía no se ejecuto. Si se puede a la inversa
## Producto natural
**INNER JOIN** : reune tuplas de las relaciones que tienen sentido, se realiza en la clausula FROM indicando las tablas involucradas de dicho producto, y luego de la sentencia ON la condición que debe cumplirse
```sql
SELECT a.nombre, a.apellido, e.nota
FROM alumno a INNER JOIN examen e ON (a.dni=e.dni)
```
**NATURAL JOIN** : análogo al producto natural de AR, trabaja por equicombinación.
>[!tip] ¿Cómo diferenciarlos?
>En el INNER indico la condición por la cual quiero cruzar, en el natural realiza todo automáticamente. En la práctica se utiliza más el inner.
>
## LEFT y RIGHT JOIN
Contiene todos los registros de la tabla de la izquierda/derecha, aún cuando no exista un registro correspondiente en la tabla de la derecha/izquierda, para uno de la izquierda/derecha. Retorna un valor nulo (NULL) en caso de no correspondencia.
```sql
SELECT *
FROM alumno a LEFT JOIN examen e ON
(a.dni=e.dni)
```
### *Buscar un mejor ejemplo...*
## UNION
La unión es igual que en el álgebra, deben ser compatibles ambas tablas. Elimina duplicados, si los quiero mantener uso UNION ALL
```sql
#Este ejemplo no tiene mucho sentido
SELECT nombre
FROM alumno
WHERE (dni > 25000000)
UNION
SELECT nombre
FROM materia
```
## EXCEPT e INTERSECT
Cláusula definida para diferencia de productos, el intersect realiza la intersección. 
>[!danger] Las tablas deben ser compatibles
```sql
SELECT dni
FROM alumno
WHERE (dni > 25000000)
EXCEPT 
SELECT dni 
FROM examen
# me quedo con los dni mayores, pero que no rindieron exámen
```
## ORDER BY
Por defecto lo ordena de menor a mayor, se puede cambiar poniendo DESC
```sql
SELECT nombre, apellido, dni
FROM alumno
WHERE (dni >230000) and (nombre = 'Luciana')
ORDER BY apellido, dni DESC
#Apellido de mayor a menor y dni de menor a mayor
```
## Funciones de agregación
Vamos a ver 5, se utilizan sobre el SELECT, operando sobre un conjunto de tuplas como entrada generando una salida.
- **AVG**: promedio del atributo indicado para todas las tuplas del conjunto
- **COUNT** : cantidad de tuplas incolucradas en el conjunto de entradas
- **MAX** : valor más grande dentro del conjunto de tuplas para el atributo indicado
- **MIN** : valor más pequeño dentro del conjunto de tuplas para el atributo indicado
- **SUM** : suma el valor del atributo indicado para todas las tuplas del conjunto
```sql
SELECT COUNT (*)
FROM empleados

SELECT MAX (salario)
FROM empleados
# lo mismo con el min

SELECT SUM (salario)
FROM empleados
```
## GROUP BY
agrupa las tuplas de una consulta por algún criterio con el objetivo de aplicar una función de agregación.
```sql
SELECT nombre, apellido, AVG(nota) as promedio
FROM alumno a INNER JOIN examen e ON (a.dni=e.dni)
GROUP BY e.dni, nombre, apellido
```
>[!danger] Recordar
>Todo lo que proyecte en el select, lo tengo que indicar en el group by (por estándar). Siempre debo agrupar por clave primaria. 
## HAVING
Permite filtrar por grupos, las funciones de agregación no se pueden usar en el where, es necesario agrupar y hacer having.
```sql
SELECT nombre, apellido, AVG(nota) as promedio
FROM alumno a INNER JOIN examen e ON (a.dni=e.dni)
GROUP BY e.dni, nombre, apellido
HAVING AVG(nota) >= 6
```
## Subconsultas
Realizar una consulta dentro de otra
- = : igualdad, cuando una subconsulta retorna un único resultado es posible compararlo contra un valor simple.
- IN : pertenencia, comprueba si un elemento es parte o no de un conjunto. Negación  (NOT IN)
- =SOME : igual a alguno
- >ALL : mayor que todos
- <=SOME : menor o igual que alguno
```sql
SELECT nombre, apellido
FROM alumno
WHERE dni IN (SELECT dni FROM examen)
WHERE nota < 4)
# muestra el nombre y apellido de los alumnos que desaprobaron un exámen

```
## Exists 
Permite saber si la subconsulta devolvió algo, devuelve true si existe false si  no. El NOT EXISTS es al revés
```sql
SELECT dni, nombre, apellido
FROM alumno a
WHERE EXISTS (SELECT * FROM examen e WHERE 
a.dni=e.dni and e.nota=10)
```
## ABM
- **INSERT INTO ... VALUES**: agrega tuplas a una tabla.
```sql
INSERT INTO alumno (dni, nombre, apellido) VALUES (233254,
'Raul', 'Perez')
# la tabla ya existe
```
- **DELETE FROM** : borra una tupla o un conjunto de tuplas de una tabla.
```sql
DELETE FROM alumno WHERE dni=2222222;
```
- **UPDATE ... SET** : modifica el contenido de uno o varios atributos de una tabla.
```sql
UPDATE alumno SET nombre 'Lorenzo' WHERE dni = 224236464
```

### *Añadir lo que falta....*
