Escrito em: 10-02-2025 08:12
# O que é e como usar
A classe File permite gerenciar arquivos e diretórios a partir de um  dado caminho.

Sua sintaxe:
```
File <apelido> = new File("<enderecoDoArquivo>");
file.<operacoesDaPropriaClasse>;
```


# Mais algumas de suas operações

listFiles() para listar um tipo de arquivo:
```
String path = "c:\\projetos"
File file = new File(path);

//Aqui lista as sub pastas apartir do caminho do diretório dado.
File[] folders = file.listFiles(File::isDirectory); //Vai listar apenas as pastas
	System.out.println("Folders:");
	for(File folder : folders) {
		System.out.println(folder);
}
//Já aqui lista os sub arquivos apartir do caminho do diretório dado.
File[] files = file.listFiles(File::isFile); //Vai listar apenas os arquivos
	System.out.println("Files:");
	for(File fil : files) {
		System.out.println(fil);
}
```

Na criação de um arquivo:
```
boolean <nomeDaVariavel> = new File(path + "\\nomeDaNovaPasta").mkdir();
//Podemos saber se criou a pasta ou não se colocar-mos a variável em um print
System.out.println("Criou com sucesso: " + <nomeDaVariavel>);
```

Para seu nome, pai (parente) e seu caminho respectivamente:
```
System.out.println("Seu nome: " + file.getName());
System.out.println("Seu pai: " + file.getParent());
System.out.println("Seu caminho: " + file.getPath());
```

Operações que retornam boolean:
```
System.out.println("Permition to read: " + file.canRead());
System.out.println("Permition to write: " + file.canWrite());
System.out.println("Permition to execute: " + file.canExecute());
```