Escrito em: 14-02-2025 09:58

tags: [[Métodos abstratos]],[[Interfaces e Herança, diferenças e junção]], [[Herança em JAVA]], [[Polimorfismo]],[[Problema do diamante e herança múltipla com interfaces]],[[Interface]]
# O que é default methods

Default/Defender methods são métodos em uma interface que podem ser reusadas sem a necessidade de implementar em uma classe.

Para criarmos um método default é só criar um método de sua preferência que como visibilidade seja default, por exemplo:
```
public interface <NomeDaInterface> {
	default void método1() {
		<BlocoDeComando>
	}
}
```

Problema exemplo: Fazer um programa para ler um valor de empréstimo e quantos meses irá pagar e como saída mostrar como o valor vai está depois dos meses ditos. O valor será definido a partir da dos juros do Brasil, mas o país pode ser mudado no futuro.

Primeiro, temos que construir o programa principal e sabemos que o valor de juros pode mudar de acordo com o país mas no momento está sendo usado o juros do Brasil.

Programa principal:![[Pasted image 20250214103340.png]]

Juros do Brasil:![[Pasted image 20250214103418.png]]

E a interface:
![[Pasted image 20250214103455.png]]

"Mas aonde está o default method?"
-Ainda não o implementamos, mas é muito fácil, tudo que temos que fazer é colocar o método payment no lugar do método da interface e removermos da BrazilInterestService:

Interface com método default: ![[Pasted image 20250214103759.png]]

BrazilInterestService:![[Pasted image 20250214103843.png]]

Agora não precisamos reescrever o método em todas as classes que implementarão a interface.

"Mas e o getInterestRate()?"
-Já que uma interface pode apenas implementar métodos e não estados, precisamos (no caso desse método) ter um valor para que seja atribuído á lógica do payment.

OBS: Note que eu não precisei modificar o programa principal mas se eu precisar mudar para um sistema de juros diferente, mudar o objeto concreto da instanciação do InterestService é o suficiente. 

# Pontos importantes

Agora que as interfaces tem a possibilidade de ter reuso, na ocorrência de ter uma classe implementar 2 ou mais interfaces, pode ser considerado herança múltipla.

Como foi dito em [[Interfaces e Herança, diferenças e junção]] para ter uma forma de reuso, tínhamos usar uma classe abstrata para complementar o programa. Em algumas situações ainda vamos temos que usar classes abstratas, por que as interfaces não podem ter atributos ou construtores mas se apenas precisamos do reuso em métodos para não implementa-los em todas as classes, podemos usar os métodos default. 
