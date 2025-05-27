# 5) Crie uma classe abstrata chamada Pessoa com aos atributos Nome e Cidade. Crie também um método abstrato chamado EfetuarCompra. Crie duas classes que herdam de Pessoa, uma chamada PessoaFIsica e outra chamada PessoaJuridica, que implementam o método EfetuarCompra. Crie atributos específicos para cada uma das novas classes, por exemplo, CPF em PessoaFisica e CNPJ em PessoaJuridica.

## Pessoa
```java
package Exercicio05;

public abstract class Pessoa {
	protected String nome;
	protected String cidade;

	public Pessoa(String nome, String cidade) {
		this.nome = nome;
		this.cidade = cidade;
	}

	public abstract void efetuarCompra();
}

```
## PessoaFisica
```java
package Exercicio05;

public class PessoaFisica extends Pessoa {
	private String cpf;

	public PessoaFisica(String nome, String cidade, String cpf) {
		super(nome, cidade);
		this.cpf = cpf;
	}

	@Override
	public void efetuarCompra() {
		System.out.println("Pessoa Física " + nome + " efetuou uma compra usando o CPF " + cpf + ".");
	}
}

```
## PessoaJuridica
```java
package Exercicio05;

public class PessoaJuridica extends Pessoa {
	private String cnpj;

	public PessoaJuridica(String nome, String cidade, String cnpj) {
		super(nome, cidade);
		this.cnpj = cnpj;
	}

	@Override
	public void efetuarCompra() {
		System.out.println("Pessoa Jurídica " + nome + " efetuou uma compra usando o CNPJ " + cnpj + ".");
	}
}

```
## Principal
```java
package Exercicio05;

public class Principal {
	public static void main(String[] args) {

		Pessoa pf = new PessoaFisica("Éric", "Santa Maria", "123.456.789-00");
		Pessoa pj = new PessoaJuridica("Centauro", "Formigueiro", "12.345.678");

		pf.efetuarCompra();
		pj.efetuarCompra();

	}
}

```
