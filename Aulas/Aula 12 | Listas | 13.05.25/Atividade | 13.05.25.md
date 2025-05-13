# Exercício 1
Crie uma classe Aluno com os atributos nome e notaFinal. Em seguida, crie uma classe Boletim com um método imprimirStatus(Aluno a) que imprime se o aluno foi aprovado (nota = 6) ou reprovado.
## Classe Aluno
```java
package Exercicio01;

public class Aluno {
	private String nome;
	private double notaFinal;
	private Boletim boletim;

	public Aluno(String nome, double notaFinal, Boletim boletim) {
		super();
		this.nome = nome;
		this.notaFinal = notaFinal;
		this.boletim = boletim;
	}

	public String getNome() {
		return nome;
	}

	public double getNotaFinal() {
		return notaFinal;
	}

	public Boletim getBoletim() {
		return boletim;
	}

}
```

## Classe Boletim
```java
package Exercicio01;

public class Boletim {
	private double notaFinal;
	
	public void imprimirStatus(Aluno a) {
		if(notaFinal >= 6)
			System.out.println("Aluno APROVADO!");
		else
			System.out.println("Aluno REPROVADO!");
	}
}
```

## Classe Principal
```java
package Exercicio01;

public class Principal {

	public static void main(String[] args) {
		// Aluno a = new Aluno("Éric", 9.5);

	}

}
```

# Exercício 2
Crie uma classe Produto com os atributos nome e preco. Em outra classe, crie um método criarProdutoDesconto(String nome, double preco) que retorna um objeto Produto com 10% de desconto aplicado ao preço.
## Classe Produto
```java
package Exercicio02;

public class Produto {
	private String nome;
	private double preco;

	public Produto(String nome, double preco) {
		super();
		this.nome = nome;
		this.preco = preco;
	}

	public String getNome() {
		return nome;
	}

	public void setNome(String nome) {
		this.nome = nome;
	}

	public double getPreco() {
		return preco;
	}

	public void setPreco(double preco) {
		this.preco = preco;
	}

}
```

## Classe Principal
```java

```

# Exercício 3
Crie uma classe Livro com os atributos titulo e autor. Em seguida, crie uma lista de livros (ArrayList) e um método que recebe a lista e imprime os dados de cada livro.
## Classe
```java

```

## Classe
```java

```

# Exercício 4
Crie uma classe Conta com os atributos titular e saldo. Crie um método depositar(Conta c, double valor) que receba a conta como parâmetro e aumente o saldo.
## Classe
```java

```

## Classe
```java

```
