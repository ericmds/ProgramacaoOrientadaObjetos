# 4) Crie uma classe abstrata chamada Veiculo com os atributos Marca, Modelo e Ano. Crie dois métodos abstratos chamados Acelerar e Frear. Crie duas classes que herdam de Veiculo, uma chamada Carro e outra chamada Moto, que implementam os métodos Acelerar e Frear.
## Veiculo
```java
package Exercicio04;

public abstract class Veiculo {
	protected String marca;
	protected String modelo;
	protected int ano;

	public Veiculo(String marca, String modelo, int ano) {
		this.marca = marca;
		this.modelo = modelo;
		this.ano = ano;
	}

	public abstract void acelerar();

	public abstract void frear();
}

```
## Carro
```java
package Exercicio04;

public class Carro extends Veiculo {

	public Carro(String marca, String modelo, int ano) {
		super(marca, modelo, ano);
	}

	@Override
	public void acelerar() {
		System.out.println("O carro está acelerando.");
	}

	@Override
	public void frear() {
		System.out.println("O carro está freando.");
	}
}

```
## Moto
```java
package Exercicio04;

public class Moto extends Veiculo {

	public Moto(String marca, String modelo, int ano) {
		super(marca, modelo, ano);
	}

	@Override
	public void acelerar() {
		System.out.println("A moto está acelerando.");
	}

	@Override
	public void frear() {
		System.out.println("A moto está freando.");
	}
}

```
## Veiculo
```java
package Exercicio04;

public class Principal {
	public static void main(String[] args) {

		Veiculo carro = new Carro("Toyota", "Corolla", 2020);
		Veiculo moto = new Moto("Honda", "CB500", 2021);

		carro.acelerar();
		carro.frear();

		moto.acelerar();
		moto.frear();

	}
}

```
