Escrito em: 05-02-2025 09:09

tags: [[Herança em JAVA]]
# O que é
A palavra chave "final" pode ser usada em classes, métodos ou em atributos, cada um tendo sua finalidade própria. 

Em métodos, significa que não pode ser sobreposto em nas subclasses.
![[Pasted image 20250205091625.png]]

Em classes, impossibilita de classes poderem herda-la.
![[Pasted image 20250205092101.png]]

E em atributos, durante momento de execução, seu conteúdo não pode ser alterado.

Também é usado para criar constantes.
![[Pasted image 20250205092151.png]]

# Ponto importante
O compilador lê uma classe final mais rápido pois ele sabe que a classe é imutável e não tem riscos de ter subclasses (O mesmo vale para métodos).