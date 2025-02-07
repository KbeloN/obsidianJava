Escrito em: 04-02-2025 11:09

Tags: [[Polimorfismo]],[[Herança em JAVA]]
# O que é

Upcasting é a instanciação de uma subclasse (Classe filha) em uma variável de um superclasse mais genérica(classe pai), ou também uma "promoção" de uma subclasse. Já o Downcasting é o contrário, nesse caso, uma superclasse se "rebaixa" ao nível de uma subclasse.

Upcasting e Downcasting:
```
//Account (Classe mais genérica)
//SavingsAccount (Classe mais específica e filha da Account)

//Upcasting
Account x = new SavingsAccount(0 , " " , 0.0);

//Downcasting
SavingsAccount y = (SavingsAccount) x;
```

# Por que usar

Upcasting pode ser usado de várias maneiras mas majoritariamente do tempo, o seu uso se dá em [[Polimorfismo]].Por outro lado, o Downcasting é usado quando (seguindo o exemplo) precisamos fazer alguma operação da classe SavingsAccount, e para essa ocasião, é necessário rebaixar-mos a variável Account para Savings account indicando ao compilador que x é uma instância de SavingsAccount. Caso x seja instância de outro tipo, ao executar o programa, daria uma Exception "ClassCastException", mas pode ser resolvido com uma simples lógica de if junto ao instanceof.

# Ponto importante

A associação do tipo mais específico para o tipo mais genérico é realizada apenas em tempo de execução.