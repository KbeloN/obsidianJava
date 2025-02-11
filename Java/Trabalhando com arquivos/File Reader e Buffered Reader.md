Escrito em: 10-02-2025 09:56

tags:[[Leitura com FileReader e BufferedReader]], [[Leitura e escrita de arquivos]], [[Exceções em Java]], [[Escrita com File Writer e Buffered Writer]]
# O que é (Resumo)
O File Reader é um sequência de leitura de caracteres dentro de um arquivo (lê de 2 a 4 bytes, dependendo dos caracteres) e só pode ser usada para ler textos. Já que o processo de leitura poderia ser muito lendo de acordo com o tamanho do arquivo, a classe Buffered Reader foi criada.

O Buffered reader (BR) foi criado para acelerar o processo de leitura. Ele serve como uma classe auxiliar. Quando é necessário ler algo, o BR chama a função do File Reader para a leitura e armazena as informações na RAM, pois assim, quando for necessário escrever esses dados em um arquivo, será SUPER mais rápido (Por a RAM ser uma memória muito rápida) do que fizéssemos de 2 a 4 bytes por vez.

Observação: Buffered Reader e Writter não são apenas usados para arquivos de texto.
# Referências:
- Como fazer a [[Leitura com FileReader e BufferedReader]] em um arquivo.
- Uma discussão no stack overflow que explica detalhadamente o que File Reader e Buffered Reader (Em inglês): https://stackoverflow.com/questions/9648811/specific-difference-between-bufferedreader-and-filereader.
