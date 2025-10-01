2025-09-25
## Sobrecarga de constructores
``` java
// constructor del general tree
public GeneralTree(T data){
	this.data = data;
}

public GeneralTree(T data, List<GeneralTree<T>> children){
	this(data);    // <------- ??????
	this.children = children;
}
```
>[!danger] Repasar el this(data)
## Recorrido preOrden
```java
// raíz, 
public class GeneralTree<T> {
	// usando iterator
	public void preOrden(){
		System.out.println(getData());
		List<GeneralTree<T>> children = this.getChildren();
		Iterator<GeneralTree<T>> child = it.next();
		while (it.hasNext()){
			GeneralTree<T> child = it.next();
			child.printPreorder();
		}
	}
	// usando for-each
	public void printPreOrder(){
		System.out.println(getData());
		List<GeneralTree<T>> children = this.getChildren();
		for (GeneralTree<T> child: children)
			child.printPreOrder();
	}
}
```
> [!tip] Es más fácil el for-each
## Recorrido por niveles 🪜
```java
public class Recorridos {
	public static <T> List <T> traversalLevel(GeneralTree<T> tree){
		List<T> result = new LinkedList<T>();
		GeneralTree<T> aux;
		
		Queue<GeneralTree<T>> queue = new Queue<>();
		queue.enqueue(tree);
		while (!queue.isEmpty()){
			aux = queue.dequeue();
			result.add(aux.getData());
			List<GeneralTree<T>> children = aux.getChildren();
			for (GeneralTree<T> child : children)
				queue.enqueue(child);
		}
		return result;
	}
}
```
> [!question] ¿Cómo controlo el nivel?
> - Repasar el ejercicio de devolver las imágenes de un nivel
> - ¿Cómo funciona el substring?

### Para casa (analizar):
- El ejercicio del árbol general de personajes
- El último ejercicio
