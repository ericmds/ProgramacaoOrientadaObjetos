# Exemplo 1
## Classe Pessoa
```java
package Exemplo01;

public class Pessoa {
	private String nome;
	private int idade;

	public Pessoa(String nome, int idade) {
		this.nome = nome;
		this.idade = idade;
	}

	public String getNome() {
		return nome;
	}

	public int getIdade() {
		return idade;
	}

}
```
## Classe Principal
```java
package Exemplo01;

public class Principal {

	public static void main(String[] args) {
		Pessoa pessoa = new Pessoa("Éric", 25);
		meuMetodo(pessoa);
	}
	
	public static void meuMetodo(Pessoa p) {
		System.out.println("Nome: " + p.getNome());
		System.out.println("Idade: " + p.getIdade());
	}

}
```

---

# Exemplo 2
## Classe Produto
```java
package Exemplo02;

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

	public Produto clone() {
		return new Produto(this.nome, this.preco);
	}

}
```

## Classe Principal
```java
package Exemplo02;

public class Principal {
	public static void main(String[] args) {
		Produto produto1 = new Produto("Caneta", 1.5);
		Produto produto2 = produto1.clone();

		System.out.println("Produto 1 - Nome: " + produto1.getNome() + ", Preço: " + produto1.getPreco());
		System.out.println("Produto 2 - Nome: " + produto2.getNome() + ", Preço: " + produto2.getPreco());

		produto2.setPreco(2.0);

		System.out.println("\nProduto 1 - Nome: " + produto1.getNome() + ", Preço: " + produto1.getPreco());
		System.out.println("Produto 2 - Nome: " + produto2.getNome() + ", Preço: " + produto2.getPreco());

	}

}
```

---

# Exemplo 3
## Classe Produto
```java
package Exemplo03;

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

	public Produto clone() {
		return this;
	}
}
```

## Classe Principal
```java
package Exemplo03;

public class Principal {
	public static void main(String[] args) {
		Produto produto1 = new Produto("Caneta", 1.5);
		Produto produto2 = produto1.clone();

		System.out.println("Produto 1 - Nome: " + produto1.getNome() + ", Preço: " + produto1.getPreco());
		System.out.println("Produto 2 - Nome: " + produto2.getNome() + ", Preço: " + produto2.getPreco());

		produto2.setPreco(2.3);

		// Os dois produtos se alteram pois o produto 2 é um clone do produto um e está retornando ele mesmo
		
		System.out.println("\nProduto 1 - Nome: " + produto1.getNome() + ", Preço: " + produto1.getPreco());
		System.out.println("Produto 2 - Nome: " + produto2.getNome() + ", Preço: " + produto2.getPreco());

		if (produto1 == produto2)
			System.out.println("São iguais");
		else
			System.out.println("São diferentes");

	}

}
```
