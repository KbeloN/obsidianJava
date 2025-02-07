Escrito em: 05-02-2025 11:04

tags: [[Herança em JAVA]], [[Polimorfismo]]
# O que é
o método abstrato é uma forma de obrigar as subclasses a implementar o tal com sua própria lógica.
# Como usar
Na superclasse:
```
//Sintaxe
<visibilidade> abstract <tipo> <nome do método>();
//Exemplo
public abstract Double area();
```

Vale destacar que é OBRIGATÓRIO que a classe seja abstract, caso ela não seja, ao criar o método ele se torna abstract.
# Por que usar
Usamos um método abstrato quanto não tem se tem uma solução definitiva para todos os problemas do conjunto, pois cada elemento (subclasse) tem sua própria regra de negócio e ele que deve saber o seu domínio (Delegação).
