Escrito em: 13-02-2025 09:34

tags: [[Herança em JAVA]], [[Polimorfismo]], [[Upcasting e Downcasting]], [[Interface]], [[Métodos abstratos]]
# O que é e suas diferenças
Como eu disse em [[Interface]], as interfaces e heranças tem coisas em comum como a relação é um, generalização/especialização e polimorfismo:![[Pasted image 20250213100539.png]]

Mas não confunda, herdar não é igual cumprir um contrato. Quando uma classe passa a implementar uma interface, ela é obrigada a adicionar seus métodos para CUMPRIR SUA PARTE DO CONTRATO. Já quando uma classe herda outra classe, acontece o REUSO onde não vai ser necessário reescrever todo o código, á não ser que tenha um método abstrato.

"Ok, mas caso eu queira usar uma interface para obrigar as classes a exercer uma ação e ainda querer usar uma herança para não ter que reescrever o código para cada subclasse, eu consigo?".
 -Sim.

# Como usa-las em conjunto

Para isso, basta criar uma classe abstrata que contenha os atributos que deseja e implementar a interface. 
"Mas por que uma classe abstrata?"
-Caso use uma classe pública por exemplo, o compilador vai te parar porque você deve cumprir o contrato, mas podemos contornar isso fazendo a classe ser abstrata e apenas as classes que herdarem dela deverão adicionar o(s) método(s).

Imagem da mensagem do compilador:![[Pasted image 20250213105108.png]]

Diagrama UML do exemplo:
![[Pasted image 20250213105036.png]]
# Por que usar
Deixa o código mais flexível e ainda temos a vantagem do reuso.