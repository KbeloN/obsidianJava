Escrito em: 05-02-2025 09:30

tags: [[Herança em JAVA]]
# O que é

Polimorfismo é a capacidade de uma variável genérica ter um comportamento diferente em um método de acordo com o tipo instanciado.
Ou
Um mesmo método ter mais de um comportamento de acordo com o tipo instanciado na variável em que foi chamado.

Exemplo:

Método na classe genérica:
```
//Classe account
public void withdraw(Double Amount){
	balance -= amount - 5.0;
}
```

Método na classe mais específica:
```
//Classe SavingsAccount extends Account
@Override
public void withdraw(Double amount){
	balance -= amount;
}
```

No main:
```
Account x = new Account(1001, "Alex", 1000.0);
Account y = SavingsAccount(1002, "Bob", 1000.0);

x.withdraw(50.0);
y.withdraw(50.0);
```

Nesse exemplo o método withdraw têm duas formas como foi demonstrado. o resultado será que a conta mais genérica ficará com o extratro de 945 e a conta mais específica ficará com 950.

# Ponto importante

Inicialmente o compilador não sabe qual é o tipo das variáveis, então é importante destacar que o tal só saberá como a variável é instanciada durante o tempo de execução(Upcasting), e assim, decidirá qual comportamento prosseguir em cada chamada de operação.
