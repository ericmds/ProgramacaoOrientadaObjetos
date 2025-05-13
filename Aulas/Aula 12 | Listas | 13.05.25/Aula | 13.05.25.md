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

# Exemplo 4
## Classe Endereco
```java
package Exemplo04;

public class Endereco {
	private String rua;
	private int numero;

	public Endereco(String rua, int numero) {
		super();
		this.rua = rua;
		this.numero = numero;
	}

	public String getRua() {
		return rua;
	}

	public int getNumero() {
		return numero;
	}
}
```

## Classe Pessoa
```java
package Exemplo04;

public class Pessoa {
	private String nome;
	private int idade;
	private Endereco endereco;

	public Pessoa(String nome, int idade, Endereco endereco) {
		this.nome = nome;
		this.idade = idade;
		this.endereco = endereco;
	}

	public String getNome() {
		return nome;
	}

	public int getIdade() {
		return idade;
	}

	public Endereco getEndereco() {
		return endereco;
	}

}
```

## Classe Principal
```java
package Exemplo04;

public class Principal {

	public static void main(String[] args) {
		Pessoa pessoa = new Pessoa("Éric", 25, new Endereco("Rua 1", 123));

		System.out.println("Nome: " + pessoa.getNome());
		System.out.println("Idade: " + pessoa.getIdade());
		System.out.println("Endereço: " + pessoa.getEndereco().getRua() + ", " + pessoa.getEndereco().getNumero());

	}

}
```

# Exemplo 5
## Classe Pessoa
```java
package Exemplo05;

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
package Exemplo05;

import java.util.ArrayList;
import java.util.List;

public class Principal {

	public static void main(String[] args) {
		List<Pessoa> listaPessoas = new ArrayList<Pessoa>();

		Pessoa pessoa1 = new Pessoa("Éric", 25);
		Pessoa pessoa2 = new Pessoa("Anna", 25);
		Pessoa pessoa3 = new Pessoa("Nala", 25);

		listaPessoas.add(pessoa1);
		listaPessoas.add(pessoa2);
		listaPessoas.add(pessoa3);

		exibirPessoas(listaPessoas);

	}

	public static void exibirPessoas(List<Pessoa> lista) {
		for (Pessoa objetoArmazenaItensDaLista : lista) {
			System.out.println("Nome: " + objetoArmazenaItensDaLista.getNome());
			System.out.println("Idade: " + objetoArmazenaItensDaLista.getIdade());
		}
	}

}
```
