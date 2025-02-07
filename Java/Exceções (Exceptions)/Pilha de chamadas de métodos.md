Escrito em: 07-02-2025 08:53

tags:[[Exceções em Java]], [[Estrutura Try-Catch]]
# O que é e como usar
Basicamente é quando ocorre uma exceção dentro de um método que está dentro de um ou mais métodos durante tempo de execução.

Podemos saber essa informação se usarmos o método "printStackTrace":

Sintaxe:
```
try{
	<bloco de comandos>
}
catch(<nomeException> <apelido>){
	<apelido>.printStackTrace();
}
```

exemplo:
```
public static void main(String[] args) {
	method1();
	System.out.println("***END OF PROGRAM***");
}
public static void method1() {
	System.out.println("***METHOD1 START***");
	method2();
	System.out.println("***METHOD1 END***");
}
public static void method2() {
	try {
		System.out.println("***METHOD2 START***");
		Scanner sc = new Scanner(System.in);
		String[] names = sc.nextLine().split(" ");
		int i = sc.nextInt();
		System.out.println(names[i]);
	}
	catch(ArrayIndexOutOfBoundsException e) {
		System.out.println("invalid position");
		e.printStackTrace();
	}
	catch(InputMismatchException e) {
		System.out.println("invalid type");
		e.printStackTrace();
	}
	System.out.println("***METHOD2 END***");
}
```

Resultado em caso de erro:
```
***METHOD1 START***
***METHOD2 START***
alex bob maria
5
invalid position
	java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 3
	at exceptions1/application.main.method2(main.java:24)<-- exception no método1
	at exceptions1/application.main.method1(main.java:14)<-- que fica dentro do método2
	at exceptions1/application.main.main(main.java:9)<-- e que foi chamado do método main
***METHOD2 END***
***METHOD1 END***
```
# Por que usar
Pode ficar mais rápido achar a posição de uma eventual exception por parte do programador e não usuário.