Escrito em: 07-02-2025 16:25

tags: [[Exceções em Java]], [[Estrutura Try-Catch]]
# O que é e como usar
Caso as exceptions padrões do Java não poderem solucionar o probrema podemos criar exceções personalizadas. Para isso temos que criar uma nova classe com o nome que queremos na exceção e estende-la com a classe classe "Exception" ou "RuntimeException".

Na hipótese de usar "Exception", terá que propagar aos métodos escolhidos que eles poderão lançar a exceção criada para o programa principal tratar, ou, trata-la no código fonte. Mas se porventura, ter escolhido "RuntimeException", as mesmas regras passadas irão se aplicar, mas com a diferença que o compilado não vai indicar que precisa propagar a exceção ou trata-la e nem vai dizer que está faltando uma estrutura catch com a tal.

# Criação e uso
Sintaxe de sua criação:
```
public class <nomeDaExceção> extends Exception ou RuntimeException{
	<Bloco de comandos>
}
```

Exemplo:
```
public class DomainException extends Exception{
		private static final long serialVersionUID = 1L; <--Uma exceção precisa ter um código de serialização
		public DomainException(String msg) { <--Seu construtor
			super(msg);
	}
}
```

Sintaxe em um método:
```
public void <nomeDoMétodo>() throws <nomeDaExceçãoPersonalizada> {
	if(<lógicaDeIf)){
		throw new <nomeDaExceçãoPersonalizada>("Mensagem que vai enviar ao programa principal");
	}
}
```

Exemplo:
```
public void updateDates(Date checkIn, Date checkOut) throws DomainException {
	if(checkIn.before(this.checkIn) || checkOut.before(this.checkOut)){
	throw new DomainException("Reservation update date must be future.");
}
if(!checkOut.after(checkIn)) {
	throw new DomainException("Check-out date must be AFTER check-in date.");
}
this.checkIn = checkIn;
this.checkOut = checkOut;
}
```



