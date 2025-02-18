Escrito em: 17-02-2025 11:49

tags:[[Curinga]], [[Curinga delimitado]], [[Generics]], [[Generics delimitados]]
# O que é e como usar

O curinga (?) pode ser qualquer tipo e usamos em algumas lógicas envolvendo métodos e listas.

Um ponto importante de saber é que os generics são invariáveis, o que implica que só podemos  altera-las se seguirmos suas regras, nesse caso, o seu tipo. Então se tentamos atribuir uma lista de inteiros em uma lista de Object, não dá certo, mesmo que a classe Integer é sub classe de Object.
```
List<Integer> myInt = new ArrayList<>();
List<Object> myObject = new ArrayList<>();

myObject = myInt (Compilador dá erro);
```

Mas se colocarmos o curinga ao invés de Object o compilador deixa atribuir.
```
List<Integer> myInt = Arrays.asList(1, 2, 3);
List<?> myObject = new ArrayList<>();

myObject = myInt;
```

OBS: Não é permitido adicionar elementos em uma lista curinga. Mais informações sobre em [[Curinga delimitado]] na parte de covariância.

Podemos usar o curinga em métodos similar a [[Generics]].
```
public void print(List<?> list){
	for(Object obj : list){
		System.out.println(list);
	}
}
```

O método print vai printar qualquer tipo de lista por ser do tipo curinga.