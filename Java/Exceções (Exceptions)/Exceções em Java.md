Escrito em: 06-02-2025 08:59
# O que é
São erros que podem acontecer em tempo de execução.
As exceções são uma extensão da classe Throwable que contem dois tipos de exceções:

- Error, que são erros que o programador não consegue consertar como um erro na maquina virtual Java (VirtualMachineError) ou falta de memória para a execução do programa (OutOfMemoryError). 

- Exceptions (Exceções) que são erros que o programador consegue e deve consertar como a "ClassCastException" (Uma exceção que ocorre quando o programador tenta instanciar Uma variável de uma classe A com a classe/tipo B que não tem conexão direta com ela. Exemplo: String i = (Integer)num15) ou "IOExcepetion" (Quando ocorre uma falha ou interrupção inesperada de entrada e saída de dados)
# Sua vantagens

- Quando ocorre uma exceção o compilador fala exatamente em qual linha o erro está.
- Podemos criar [[Exceções personalizadas]] para resolver problemas específicos de um domínio.
- Uma boa prática é a delegação, o que significa que quem deve saber a regra de negócio é a própria classe e não o programa principal. 

# Relacionados
- [[Exceções personalizadas]]
- [[Estrutura Try-Catch]]
- [[Pilha de chamadas de métodos]]