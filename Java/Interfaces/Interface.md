Escrito em: 12-02-2025 11:04

tags: [[Herança em JAVA]], [[Polimorfismo]], [[Upcasting e Downcasting]]
# O que é e como usar
Uma interface é como se fosse um contrato onde a classe que a implementa essa interface, deve desempenhar certas ações (métodos). Em outras palavras, ela age como uma classe abstrata. 

Imagine um programa de aluguel de carros onde a classe que cria a fatura seja dependente da classe onde é calculado a taxa de um determinado país, que nesse caso é o Brasil.

Diagrama UML do problema:![[Pasted image 20250212121248.png]]

Classe do serviço de aluguel:
![[Pasted image 20250212123124.png]]

Programa principal:![[Pasted image 20250212123157.png]]

Agora imagine que o mesmo sistema vai ser usado com o sistema de taxa dos EUA. E graças ao forte acoplamento ao sistema de taxa brasileiro, nós teremos que mudar a classe de fatura para a adequarmos a mudança.

Mas podemos resolver isso fazendo com que o RentalService seja dependente de uma interface que tenha como contrato uma operação de calcular os impostos e implementa-la nos sistemas de taxas dos países desejados. Esse processo é similar a [[Herança em JAVA]]. 

Diagrama UML do problema (Com a interface):![[Pasted image 20250212155312.png]]

Classe do serviço do aluguel (Com a interface):![[Pasted image 20250212155517.png]]

OBS: Já que no construtor do RentalService está a interface (Classe genérica), todas as classes que cumpriram o contrato são válidas para serem usadas como argumento na instanciação do RentalService. Um ponto importante, além de herança, também conseguimos ver [[Polimorfismo]] e [[Upcasting e Downcasting]].

Exemplo de uma classe que implementa uma interface:![[Pasted image 20250212155827.png]]

E para mudarmos o sistema de imposto, basta trocar a instanciação concreta do sistema de contribuição na instanciação do RentalService:![[Pasted image 20250212162339.png]]
# Por que usar
Se usarmos uma interface ao invés de um classe de dependência, elaboraremos um código com baixo acoplamento (Classes não dependerem de outras classes para serem executadas), exerceremos a [[Inversão de controle e Injeção de dependência]] e o deixamos mais flexível caso haja mais mudanças no futuro.