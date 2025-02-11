Escrito em: 10-02-2025 08:49

tags: [[Classe File]], [[Leitura e escrita de arquivos]], [[Exceções em Java]]
# O que é e como usar
# Scanner
Podemos instanciar um scanner com um objeto file que contém o caminho para o arquivo e lê-lo.

Sua sintaxe:
```
File <apelido> = new File("<caminhoDoArquivo>");
Scanner sc = new Scanner(<objetoFile>);
```

Agora, para um forma de ler o arquivo, podemos criar uma estrutura while() com o método do scanner hasNextLine() para saber se dentro do arquivo ainda há outra linha, e, caso tenha, a lógica dentro do block while executará.

Sintaxe e exemplo:
```
File <apelido> = new File("<caminhoDoArquivo>");
Scanner sc = new Scanner(<objetoFile>);
while(sc.hasNextLine()){
	System.out.println(sc.nextLine());
}
sc.close();
```


No entanto, devemos ter cuidado, pois caso o arquivo não exista, o programa irá lançar um a exceção "IOException"(Erro na entrada e saída de dados), e consequentemente o programa vai quebrar. Para resolvermos isso podemos instanciar o scanner dentro de um bloco try-catch.

Sintaxe e exemplo:
```
File file = new File("c:\\arquivoDeTexto");
Scanner sc = null;
try{
	sc = new Scanner(file);
	while(sc.hasNextLine()){
	System.out.println(sc.nextLine());
	}
}
catch(IOException e){
	System.out.println("Error: " + e.getMessage());
}
finally{
	if(sc != null){
		sc.close();
	}
}

//OBS: Além do IOException, caso o scanner não seja instanciado e tentarmos fecha-lo, o programa vai quebrar com a exceção "NullPointerException", mas podemos contornar essa exceção com uma simples estrutura if para verificar se ele realmente é nulo ou não.
```
