Escrito em: 10-02-2025 09:43

tags: [[Leitura e escrita de arquivos]], [[Classe File]], [[File Reader e Buffered Reader]], [[Estrutura Try-Catch]], [[Escrita com File Writer e Buffered Writer]]

Explicação de [[File Reader e Buffered Reader]].
# Como usar
A estrutura que iremos usar é similar ao da [[Leitura com Scanner]].

Primeiro criamos uma variável String que contenha o caminho do arquivo, depois criamos as variáveis do File Reader e Buffered Reader nulos.

```
String path = "c:\\texto.txt";
FileReader fr = null;
BufferedReader br = null;
```

Agora iremos instancia-los dentro de um bloco try-catch, pois caso não exista um arquivo onde o caminho está apontando, o programa irá jogar a exceção IOException.

OBS: Podemos instancia-los manualmente ou tudo numa coisa só para deixar o código mais limpo.

```
String path = "c:\\texto.txt";
FileReader fr = null;
BufferedReader br = null;
try{
	//Manual
	fr = new FileReader(path);
	br = new BufferedReader(fr);
	//Tudo em uma linha
	br = new BufferedReader(new FileReader(path)); 
	//Caso use tudo em uma linha, não será necessário a criação da variável do FileReader
}
catch(IOException e){
	System.out.println("Error: " + e.getMessage());
}
```

Para lermos os arquivos:
```
String path = "c:\\texto.txt";
BufferedReader br = null;
try{
	br = new BufferedReader(new FileReader(path)); 
	String line = br.readLine();
	while(line != null){
		System.out.println(line);
		line = br.readLine();
	}
}
catch(IOException e){
	System.out.println("Error: " + e.getMessage());
}
```

OBS: Quando instanciamos o BufferedReader com o FileReader como parametro, todos od métodos do FileReader podem ser usados pelo BufferedReader.

Agora precisamos fecha-los, para isso usaremos o bloco Finally.
```
//Caso tenha criado as variáveis manualmente, o código pode ficar parecido com algo assim:
finally {
	try {
		if(br != null) {
			br.close();
		}
		if(fr != null) {
			fr.close();
		}
	}
	catch(IOException e){
		e.printStackTrace();//<--printStackTrace() para saber o que fez esse erro acontecer
	}
}

//Mas se colocou tudo em uma linha
finally {
	try {
		if(br != null) {
			br.close();
		}
	}
	catch(IOException e){
		e.printStackTrace();
	}
}
```
Note que eu precisei colocar um lógica inteira para tentar fecha-los pois pode dar um IOException.

Eu expliquei uma forma melhor de resolver isso deixando o código mais limpo e fácil de ler em [[Estrutura try-with-resources]].