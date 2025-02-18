Escrito em: 14-02-2025 14:01

tags:
# O que é e como usar

Generics é um recurso em JAVA que permite a reutilização de código a partir da generalização de classes.

Problema exemplo (Sem generics): Fazer um programa que leia uma quantidade N de números e mostre no final seu conteúdo e qual foi o primeiro número.

Programa principal:
```
public static void main(String[] args) {
	Locale.setDefault(Locale.US);
	
	try (Scanner sc = new Scanner(System.in)){
		System.out.print("How many values: ");
		Integer values = sc.nextInt();
		
		PrintService ps = new PrintService();
		
		for(int i = 0; i < values; i++) {
		ps.addItem(sc.nextInt());
		}
		
		ps.print();
		System.out.println("First one: " + ps.first());
	}
	catch (IllegalStateException e) {
		System.out.println("Error: " + e.getMessage());
	}
```

Classe que vai realizar as operações:
```
public class PrintService {
	List<Integer> list = new ArrayList<>();
	
	public PrintService() {
	
	}
	
	public void addItem(Integer element) {
		list.add(element);
	}
	
	public Integer first() {
		if(list.isEmpty()) {
			throw new IllegalStateException("The list need to have something");
		}
		return list.get(0);
	}
	
	public void print() {
		System.out.print("[");
		if(!list.isEmpty()) {
			System.out.print(list.get(0));
		}
		for(int x = 1; x < list.size(); x++) {
			System.out.print(", " + list.get(x));
		}
		System.out.println("]");
	}
}
```

Com esse código o problema vai estar resolvido, mais pode a vir outro problema. Se por alguma ocorrência queremos usar esse código listar Strings, como é que faz? Sem o generics, teríamos que criar uma nova classe tendo todas as operações da primeira, com a diferença de usar String.

Como outra opção, podemos fazer com que os métodos recebam parâmetros do tipo Object (Tudo do java é derivado do Object), mas seria um trabalhão porque caso precisarmos atribuir um valor a um variável precisamos fazer o downcasting por esse tipo ser uma subclasse do Object. Um ponto importante é a performance, pois o compilador tem que verificar o casting durante o tempo de excução. Além de tudo, ainda temos a questão do type security (segurança de tipos) que se usarmos Object o compilador não vai te barrar caso tente adicionar um String em uma lista de Integer.

"Tá mas como fica com o genérics?"
Com generics precisamos apenas informar que a classe e parâmetros podem ser de qualquer tipo.

Sintaxe e exemplo da classe genérica com generics:
```
public class PrintService<T> {
	List<T> list = new ArrayList<>();
	
	public PrintService() {
	
	}
	
	public void addItem(T element) {
		list.add(element);
	}
	
	public T first() {
		if(list.isEmpty()) {
			throw new IllegalStateException("The list need to have something");
		}
		return list.get(0);
	}
	
	public void print() {
		System.out.print("[");
		if(!list.isEmpty()) {
			System.out.print(list.get(0));
		}
		for(int x = 1; x < list.size(); x++) {
			System.out.print(", " + list.get(x));
		}
		System.out.println("]");
	}
}
```

OBS: Pode-se colocar qualquer letra ou palavra, basta colocar esse nome em todos os parâmetro que precisem ser modificados.

"Ok, a classe tá ai, mas como posso usa-la?"

Agora, no programa principal, (Seguindo o exemplo anterior) é só colocar o tipo desejado na classe e mudar o tipo de scanner e variável que enviará para os métodos.

Sintaxe e exemplo com generics no programa principal:
```
public static void main(String[] args) {
	Locale.setDefault(Locale.US);
	
	try (Scanner sc = new Scanner(System.in)){
		System.out.print("How many values: ");
		String values = sc.next();
		
		PrintService<String> ps = new PrintService<>();
		
		for(int i = 0; i < values; i++) {
		ps.addItem(sc.next());
		}
		
		ps.print();
		System.out.println("First one: " + ps.first());
	}
	catch (IllegalStateException e) {
		System.out.println("Error: " + e.getMessage());
	}
```
# Por que usar
O código fica mais flexível á mudanças e promove reuso.