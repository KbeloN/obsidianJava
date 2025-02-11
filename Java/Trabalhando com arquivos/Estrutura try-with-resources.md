Escrito em: 10-02-2025 15:23

tags: [[Leitura com Scanner]], [[Estrutura try-with-resources]], [[Leitura e escrita de arquivos]]
# O que é e como usar
A estrutura try-with-resources é literalmente o try-catch, mas com a possibilidade de instanciar um ou mais recursos no bloco try, assim, quando o mesmo acabar, os recursos vão ser fechados e o programa vai continuar como deveria.

Para exemplo, vamos pegar o exemplo da [[Leitura com FileReader e BufferedReader]] que lembrando, é similar ao [[Leitura com Scanner]]:
```
public static void main(String[]args) {
	String path = "c:\\ProjetosJava\\arquivosScanner\\in.txt";
	BufferedReader br = null;
	try {
		br = new BufferedReader(new FileReader(path));
		String line = br.readLine();
		while(line != null) {
		System.out.println(line);
		line = br.readLine();
	}
	}
	catch(IOException e){
		System.out.println("Error: " + e.getMessage());
	}
	finally {
		try {
			if(br != null) {
				br.close();
		}
		}
		catch(IOException e){
			e.printStackTrace();
		}
		//O try-catch é usado porque quanto o programa tentar fechar o br mas pode dar a exceção IOException e como ela é uma extensão da classe exception, devemos trata-la.
	}
}
```

Agora o mesmo exemplo, mas com o try-with-resources:
```
public static void main(String[]args) {
	String path = "c:\\in.txt";
	try (BufferedReader br = new BufferedReader(new FileReader(path))) {
		while(line != null) {
		System.out.println(line);
		line = br.readLine();
	}
	}
	catch(IOException e){
		System.out.println("Error: " + e.getMessage());
	}
```

Não precisamos de um bloco finally gigante no final e não precisamos criar uma variável antes do try pra assim instancia-la no final do código.