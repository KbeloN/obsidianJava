Escrito em: 13-02-2025 14:46

tags:[[Interface]]
# O que é e como usar
A interface comparable é uma interface que como contrato, tem um método para comparar um objeto com outro objeto.

Imagine que em um programa exista um vetor de Strings de nomes e precisamos organiza-la em ordem alfabética. Quando quando adicionamos os nomes, as variáveis tem que se comparar entre si para saber quem é antes de quem e vice versa. E a operação que nós precisamos é a Collections.sort().

# Organização com Collections.sort()

O Collections.sort é um método que organiza listas dependendo do seu tipo.

Sua sintaxe e exemplo:
```
List<String> list = new arrayList<>();
list.add("eita");
list.add("boboca");
list.add("rapaz");
Collections.sort(list);
//Nesse cenário, o sort vai organizar em ordem alfabética

List<Integer> list = new ArrayList<>();
list.add(4);
list.add(3);
list.add(5);
Collections.sort(list);
//Nesse será ordem crescente
```

Mas se colocarmos uma lista que tenha uma classe, o compilador irá te barrar por que a classe deve ser comparável e é ai que o comparable entra.

# Como usar o comparable

Primeiro temos que implementar em uma classe.

Sintaxe e exemplo:
```
public class Employees implements Comparable<Employees>
// implements Comparable<Com O Que Quer Comparar>, nesse caso eu quero comparar Employees com Employess
```

Após sua implementação precisamos cumprir o contrato criando o seu método.

Sintaxe e exemplo:
```
@Override
public int compareTo(<TipoDoObjeto> <apelido>) {
	return <Atributo>.compareTo(<apelido>.<atributo/getAtributo()>);
}

@Override
public int compareTo(Employees other) {
	return name.compareTo(other.getName());
	/*Eu quero comparar um nome de um objeto do tipo Employees com outro nome de um objeto do mesmo tipo*/
}
```

Agora se tentarmos organizar a lista, o compilador não nos barrará e vamos ter o resultado esperado.

BONUS: Se por um acaso queira organizar uma lista de números é só trocar por atributos do tipo número. E se quiser na forma decrescente, coloque um sinal de menos antes do primeiro atributo.
