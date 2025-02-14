Escrito em: 06-02-2025 10:57

tags: [[Exceções em Java]], [[Estrutura try-with-resources]]
# O que é e como usar
Essa estrutura serve para pegar/catch alguma exceção específica ou genérica que pode ocorrer no programa durante a sua execução e trata-la do jeito que acharmos melhor.

Sua sintaxe:
```
try{
	<Bloco de comandos>;
	<Bloco de comandos>;
	<Bloco de comandos>;
	<Bloco de comandos>;
	<Bloco de comandos>;
} 
catch (<nomeDaExceção> <apelido>){
	<Bloco de comandos para tratar exceção>;
}
catch (<nomeDaExceção> <apelido>){
	<Bloco de comandos para tratar exceção>;
}
...
```
Exemplo:
```
Scanner sc = new Scanner(System.in);
try{
	System.out.print("Digite um número INTEIRO: ");
	int num = sc.nextInt();
} 
catch (InputMismatchException e){
	System.out.println("Tú é burro?É pra colocar um numero inteiroKKKKKKKKKKKKKKKKKKKKK");
}
```

E por ultimo, o bloco finally. Geralmente usamos ele para fechar recursos como o scanner, e o colocamos no final do programa. Independente de como o programa for desligado ou o que vai acontecer em tempo de execução, o bloco finally vai ser executado no final.

Exemplo:
```
Scanner sc = new Scanner(System.in);
try{
	System.out.print("Digite um número INTEIRO: ");
	int num = sc.nextInt();
} 
catch (InputMismatchException e){
	System.out.println("Tú é burro?É pra colocar um numero inteiroKKKKKKKKKKKKKKKKKKKKK");
}
finally{
	sc.close();
}
```

# Por que usar
Caso queremos que o programa não feche ao dar um erro, podemos usar o try-catch para tratar a exceção e continuar a execução do programa.
Podemos também criar [[exceções personalizadas]] para suprir uma necessidade que não esteja na biblioteca do JAVA.