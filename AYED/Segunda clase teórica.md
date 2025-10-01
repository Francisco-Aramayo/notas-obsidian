8/9/25
## Arboles binarios
### Definición
Conjunto de nodos en los cuales
- Puede estar vacío
- Puede estar formado por un nodo Raíz y dos sub-árboles. Las raíces de estos van a ser hijos de la raíz (por medio de una arista)
### Descripción y terminología
- Cada nodo puede tener a lo sumo dos nodos hijos
- Cuando un nodo no tiene hijos se llama **hoja**
- Los nodos con mismo padre son **hermanos**

### Conceptos a usar
- **Camino**: secuencia de nodos desde n1 hasta nk, la longitud de ese camino esta dada por la cantidad de aristas
>[!note]
>Existe un camino de longitud cero desde cada nodo a si mismo, y existe un único camino desde la raíz a cada nodo
- **Profundidad**: es el único camino desde la raíz hasta nodo x, la profundidad de la raíz es 0
- **Grado**: es el número de hijos de un nodo
- **Altura**: Longitud más larga desde el nodo hasta una hoja
>[!note]
>Las hojas tienen altura cero y a altura de un árbol es el nodo raíz.
- **Ancestro/Descendiente**: los nodos que están relacionados con el nodo i en todo el árbol (conectados por aristas)
![[Pasted image 20250908171029.png]]

>[!tip] Balance en árboles
>Un árbol no balanceado tiene ramas con diferente cantidades de nodos, lo cual afecta directamente al orden de las operaciones que realizamos con los mismos. Para que un árbol sea balanceado la altura de cada nodo del árbol no debe superar 1

*Revisar definición*
### Árbol binario lleno
Un árbol binario es lleno si cada nodo interno tiene grado 2 y todas las hojas están al mismo nivel. La cantidad de nodos de un árbol binario lleno se puede calcular sabiendo:
**Teniendo altura h**:
$$
N  = (2^h+1-1)
$$
** corregir la fórmula
>[!tip] Definición recursiva
>1.- T es un nodo simple (árbol binario lleno de altura 0), o
   2.- T es de altura h y sus sub-árboles son llenos de altura h-1.
   
![[Pasted image 20250908171226.png]]
>[!tip] Concepto general
>Un árbol es lleno cuando cada nodo tiene la cantidad máxima de hijos que puede tener
### Árbol binario completo
Tiene que ser un árbol lleno de altura h-1 (anteultimo nivel) y el último nivel se completa de izquierda a derecha.
La cantidad de nodos varía entre:
$$
(2h) y (2^(h-1) - 1)
$$
** REVISAR FÓRMULA


### Representación
Cada nodo tiene información propia del nodo y una referencia por cada hijo

### Recorridos
#### PreOrden
```Java
public void preorden() {
	imprimir (dato);
	si (tiene hijo_izquierdo)
		hijoIzquierdo.preorden();
	si (tiene hijo_derecho)
		hijoDerecho.preorden();
}
```
#### InOrden
```Java

```
#### PostOrden
```Java

```
#### Por niveles
```Java
public void porNiveles() {
	encolar(raíz);
	mientras (cola no se vacíe) {
		desencolar(v);
		imprimir (dato de v);
		si (tiene hijo_izquierdo)
			encolar(hijo_izquierdo);
		si (tiene hijo_derecho)
			encolar(hijo_derecho);
	}
}
```

### Adjuntar la implementación en java


# Leer los ejemplos de valencias y consultarlo???
# Realizar la ejercitación del final


--- 
