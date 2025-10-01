4/9/25

## Tipo de dato abstracto
Son tipos de datos definidos por el usuario que especifican el comportamiento de un conjunto de datos, sin revelar su implementación subyacente. 
Solo definido en termino de sus operaciones.
### Características
- **Abstracción**: Permite trabajar con estructuras de datos complejas a un alto nivel. Uno solo debe saber que métodos están implementados, sin necesidad de conocer como. El ejemplo más común son las estructuras  ArrayList o LinkedList y sus respectivos métodos add(), remove() o get().
- **Reusabilidad**: Cuando un tipo de dato está bien diseñado, se puede reutilizar en diferentes partes de un programa o proyectos
### Ejemplo
Se implementan usando **interfaces** y **clases abstractas**. 
- **Lista**: La intefaz List es el TDA. Las clases ArrayList y LinkedList son implementaciones concretas de ese TDA, cada una con sus ventajas. 
--- 
## Listas
Colección ordenada de elementos. A diferencia del arreglo, su tamaño es dinámico y puede crecer o reducirse según sea necesario.
**Las operaciones principales son**:
- Insertar elemento
- Eliminar elemento
- Obtener elemento
- Buscar elemento
## Pilas
Estructura de datos que sigue el principio LIFO, se explica usando una pila de platos.
**Las operaciones principales son**:
- Push
- Pop
- Top
- isEmpty
## Colas
Estructura de datos que sigue el principio FIFO, se explica usando una fila para comprar.
**Operaciones principales**:
- Enqueue
- Dequeue
- isEmpty
--- 
## Framework de Java
 **Framework de Java**: Es una **estructura de trabajo** que organiza cómo se construye una aplicación. No es una simple colección de herramientas; te da un esqueleto y un conjunto de reglas a seguir. El **Java Collections Framework (JCF)** es un ejemplo de esto, ya que define la arquitectura para manejar colecciones de datos.
## API de Java
**API de Java**: Es un conjunto de **clases, interfaces y métodos** predefinidos (una "caja de herramientas"). El JCF es una parte de esta API. Es lo que te permite usar funcionalidad ya programada. La interfaz `java.util.Collection` es una de estas herramientas.
## Objeto tipo collection
**Objeto Tipo `Collection`**: Es una **instancia concreta** de una clase que implementa la interfaz `Collection`. Es el "resultado final" en tu código, el lugar donde realmente guardas tus datos. Ejemplos de objetos tipo `Collection` serían un `ArrayList`, un `HashSet` o un `LinkedList`.
 o un `LinkedList`.
## Upcasting y Downcasting
Cuando se realiza upcasting, se convierte un objeto de la subclase a una referencia de la superclase.
- Automático, seguro.
- Solo se accede a lo definido en la superclase
```java
Animal a = new Perro(); // upcasting
```
Con el downcasting convertimos una referencia de una superclase a una subclase.
- Manual (hay que poner (Clase)), riesgoso.
- Puede lanzar ClassCastException
```java
Perro p = (Perro) a; // downcasting
```
## Tipo de dato genérico
Son una forma de escribir clases, interfaces y métodos que pueden trabajar con distintos tipos de datos sin perder seguridad de tipos.
>[!NOTE]- Ejemplo
>Se puede ver como una caja. Esta puede contener manzanas, naranjas o libros, pero la caja en sí es siempre la misma. Solo cambia el contenido.
### Implementación
```Java
class Caja<T> {
    private T contenido;

    public void guardar(T objeto) {
        contenido = objeto;
    }

    public T obtener() {
        return contenido;
    }
}
```
### ¿Por qué existen?
Antes de que java tuviera genéricos, las colecciones como ArrayList trabajaban con Object. Entonces uno debía hacer casting manual, lo que podía causar errores en tiempo de ejecución.
### Ventajas
- El compilador chequea el tipo en tiempo de compilación
- No hace falta downcasting explícito
- El código es más seguro y reutilizable
## ArrayList vs LinkedList

| ArrayList                                             | LinkedList                                                                         |
| ----------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Internamente usa un array dinámico                    | Usa una lista doblemente enlazada                                                  |
| Acceder a un elemento por posición es muy rápido O(1) | Acceder a un elemento por posición es lento O(n)                                   |
| Insertar o borrar al final es rápido                  | Insertar o borrar en cualquier posición es rápido (si se tiene la referencia) O(1) |
| Insertar o borrar en el medio es lento O(n)           | Consume más memoria porque cada nodo guarda referencias extras.                    |
| Consume menos memoria que un LinkedList               |                                                                                    |
- ArrayList = rápido para leer por índice, más compacto en memoria.
- LinkedList = rápido para muchas inserciones/borrados en el medio, pero más costoso en memoria y acceso
## 3 Métodos para copiar colecciones
### Constructor de colección
```Java
List<String> original = new ArrayList<>();
original.add("A");
original.add("B");

List<String> copia = new ArrayList<>(original);
```
Realiza una copia superficial, copiando las referencias de los elementos, no los objetos en sí.
### Método addAll( )
```java
List<String> copia = new ArrayList<>();
copia.addAll(original);
```
El resultado es igual que el constructor: otra lista con los mismos elementos (shallow copy).
### Método clone( )
```java
ArrayList<String> copia = (ArrayList<String>) ((ArrayList<String>) original).clone();

```
También es  una copia superficial pero se requiere castear

>[!warning] Importante
>Estas 3 son copias superficiales. Si se necesita copiar los objetos internos y no las referencias hay que hacerlo manualmente o usar librerías
## Objeto iterador
Sirve para recorrer todos los elementos de una colección uno por uno, sin importar cómo está implementada(ArrayList, HashSet, etc)
### Métodos principales
- hasNext( ): devuelve true si queda uno más por recorrer
- next( ): devuelve el siguiente elemento
- remove( ): elimina el último elemento
>[!note] Ejemplo
``` java
List<String> nombres = new ArrayList<>();
nombres.add("Ana");
nombres.add("Luis");
nombres.add("Marta");

Iterator<String> it = nombres.iterator();

while (it.hasNext()) {
    String nombre = it.next();
    System.out.println(nombre);
}
```
## Cuando usar iterador o for-each
**For-each**
- Más corto y legible.
- Útil para recorrer todos los elementos sin modificar la colección.
- No podés eliminar elementos mientras se itera
- No se conoce la posición del elemento en la colección
**Iterator**
- Más flexible, permite eliminar mientras se recorre
- Da más control sobre la iteración
- Es util para detener la iteración en el medio o hacer modificaciones.

