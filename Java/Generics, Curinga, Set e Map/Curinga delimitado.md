Escrito em: 17-02-2025 11:44

tags: [[Curinga]]
# O que é e como usar

Ele é similar ao [[Generics delimitados]]. Podemos especificar quais tipos vão ser usados.
Exemplos: 
? extends Object (Um Object ou uma classe que herde object).
? super Number (Um Number ou uma superclasse de Number).
# Covariância e contravariância (Princípio get/put)

Com a covariância podemos acessar o seu conteúdo mas não podemos adicionar:
Exemplo sem erros:
```
public static void main(String[]args){
	List<Integer> intList = new ArrayList<>();
	List<Double> doubleList = new ArrayList<>();
	
	print(intList);
	print(doubleList);
}
public static void print(List<? extends Number> list){
	for(Object obj : list){
		System.out.println(list);
	}
}
```

Exemplo com compilador dando erro:
```
public static void main(String[]args){
	List<Integer> intList = new ArrayList<>();
	List<Double> doubleList = new ArrayList<>();
	
	print(intList);
	print(doubleList);
}
public static void print(List<? extends Number> list){
	list.add(2);//Compilador vai te barrar.
	for(Object obj : list){
		System.out.println(list);
	}
}

Number x = intList.get(0);
Number x = doubleList.get(0);
//podemos atribui-las pois ambos int e double são subclasses do Number.
```

"Por que não podemos adicionar a lista?"
-Vamos seguir o exemplo anterior. Eu mando printar minha lista de Integer e tento adicionar mais um elemento int, na teoria deveria funcionar pois ambos são do mesmo tipo e subclasses de Number mas como a lista do método é do tipo curinga, mesmo que eu tentar adicionar uma elemento, o compilador nos barra porque ele não sabe que tipo de lista vai ser usada no método, consequentemente não vai saber se o elemento que vamos adicionar será compatível com a lista. 

Já Contravariância é o contrario, podemos adicionar mas não podemos atribuir essa lista.
```
List<? super Number> list = new ArrayList<>();

list.add(12);

Number x = list.get(0);//não permitido

//Não podemos atribuir um elemento da lista na variável x porque pode acontecer de algum elemento ser de uma subclasse de Number (No caso Object),ai programa pode dar erro por esse downcasting não tratado.
```

