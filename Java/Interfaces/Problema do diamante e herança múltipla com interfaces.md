Escrito em: 13-02-2025 11:16

tags:[[Interface]], [[Herança em JAVA]],[[Polimorfismo]]
# O que é o problema do diamante

O problema do diamante é quando uma classe quer herdar o conteúdo de outras duas classe que herdaram outra classe, resumindo, está tentando forçar um herança multipla, quando uma classe herda de mais de uma classe. Exemplo em um diagrama UML:![[Pasted image 20250213112439.png]]

"Por que isso é um problema?".
-A herança múltipla pode ser problemática ao ponto que linguagens de programação não permitirem que isso aconteça. 

Imagine o seguinte, a classe A têm um método A, as classes classes C e B herdam esse método e após isso elas o modificam para cada um ter um comportamento diferente ([[Polimorfismo]]). Daí, criamos uma classe D que queira herdar da classe C e B, qual método que foi herdado da classe A vai ser herdado pra classe D? Ai que tá o problema, não têm como saber, e é por isso que não pode.

# "Herança múltipla" com interfaces

Seguindo o exemplo, para fazermos herança múltipla com interfaces é muito simples.

Primeiro criamos as interfaces com os métodos e a implementamos na classe que vai ter um herança múltipla. Aí se quiser, também pode herdar de um classe para mais métodos e reuso de código. Diagrama em UML:![[Pasted image 20250213120944.png]]

Assim temos todos os métodos e atributos de uma herança múltipla sem que o compilador nos barre.

# Por que não é realmente um herança múltipla

Uma herança múltipla implica que uma classe vai herdar de duas ou mais classes onde vai ser possível se realizar o reuso, e como a interface é um contrato, não se aplica ao termo.

Mas é possível uma interface ter herança múltipla e ter reúso com [[Default Methods (Defender methods)]]. 