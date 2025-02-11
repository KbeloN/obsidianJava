Escrito em: 10-02-2025 16:07

tags: [[File Reader e Buffered Reader]], [[Leitura com FileReader e BufferedReader]], [[Estrutura try-with-resources]]
# O que é e como usar
Seu funcionamento é igual ao [[File Reader e Buffered Reader]] mas ao invés de ler, vamos escrever. E usaremos a [[Estrutura try-with-resources]].
Para escrever em um arquivo o BW têm seus próprios métodos, o "write()" para escrever na linha e "newLine()" que é para pular a linha.

Exemplo e sintaxe: 
```
String [] list = new String[] {"eita", "nós", "gente"};
String path = "c:\\ProjetosJAVA\\arquivosFW_BW\\in.txt";

//new FileWriter(path,true) == adicionar mais informações nas últimas linhas
//new FileWriter(path) == criar ou refazer o arquivo do zero
try (BufferedWriter bw = new BufferedWriter(new FileWriter(path,true))) {
	String line;
	for(String obj : list) {
		bw.write(obj);
		bw.newLine();//
	}
} 
catch (IOException e) {
	e.printStackTrace();
}
```
