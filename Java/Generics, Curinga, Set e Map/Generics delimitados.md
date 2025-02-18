Escrito em: 17-02-2025 08:44

tags: [[Generics]], [[Interface Comparable e Organização]], [[Curinga]]
# O que é 

Generics delimitados, são usados em métodos genéricos que devem aceitar apenas tipos genéricos mais específicos.
# Como usar

Sua sintaxe e exemplo:
```
          /*Lógica do generics delimitado*/
public <T extends Comparable<T>> T <NomeDoMetodo>(<T>) {
// Se lê esse método vai trabalhar com qualquer tipo T caso o tipo T seja um tipo comparável. Pode colocar outros especificações, mas vamos ficar só com o comparable pra esse exemplo.

public static <T extends Comparable<T>> T max(List<T> list) {
	if(list.isEmpty()) {
		throw new IllegalStateException("The list must heva something.");
	}
	T max = list.get(0);
	for(T item : list) {
		if(item.compareTo(max) > 0) {
			max = item;
		}
	}
	return max;
}
```

No exemplo dado, precisamos especificar que o T tem que ter implementado comparable pois dentro do método nós usamos a operação compareTo() que é da interface. Se não especificarmos, o compilador nos barra falando que o tipo T não está definido.

Por último, sua declaração completa:
```
public <T extends Comparable<? super T>> T <NomeDoMetodo>() {
//Se lê esse método vai trabalhar com T caso o T seja um tipo comparável ou alguma de super classe de T
```
