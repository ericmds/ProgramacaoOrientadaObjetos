# Animal
```java
package Pkg6;

public abstract class Animal {
	protected float peso;
	protected int idade;
	protected int membros;

	public abstract void locomover();

	public abstract void alimentar();

	public abstract void emitirSom();

	public float getPeso() {
		return peso;
	}

	public void setPeso(float peso) {
		this.peso = peso;
	}

	public int getIdade() {
		return idade;
	}

	public void setIdade(int idade) {
		this.idade = idade;
	}

	public int getMembros() {
		return membros;
	}

	public void setMembros(int membros) {
		this.membros = membros;
	}

}

```
# Mamifero
```java
package Pkg6;

public class Mamifero extends Animal {
	private String corPelo;

	@Override
	public void locomover() {
		System.out.println("Correndo");

	}

	@Override
	public void alimentar() {
		System.out.println("Mamando");

	}

	@Override
	public void emitirSom() {
		System.out.println("Som de mamifero");

	}

	public String getCorPelo() {
		return corPelo;
	}

	public void setCorPelo(String corPelo) {
		this.corPelo = corPelo;
	}

}

```
# Ave
```java
package Pkg6;

public class Ave extends Animal {
	private String corPena;

	@Override
	public void locomover() {
		System.out.println("Voando");

	}

	@Override
	public void alimentar() {
		System.out.println("Comendo frutas");

	}

	@Override
	public void emitirSom() {
		System.out.println("Som de ave");

	}

	public void fazerNinho() {
		System.out.println("Construindo ninho");
	}

	public String getCorPena() {
		return corPena;
	}

	public void setCorPena(String corPena) {
		this.corPena = corPena;
	}

}

```
# Peixe
```java
package Pkg6;

public class Peixe extends Animal {
	private String corEscama;

	@Override
	public void locomover() {
		System.out.println("Nadando");

	}

	@Override
	public void alimentar() {
		System.out.println("Comendo substancias");

	}

	@Override
	public void emitirSom() {
		System.out.println("Soltando bolha");

	}

	public String getCorEscama() {
		return corEscama;
	}

	public void setCorEscama(String corEscama) {
		this.corEscama = corEscama;
	}
}

```
# Reptil
```java
package Pkg6;

public class Reptil extends Animal {
	private String corEscama;

	@Override
	public void locomover() {
		System.out.println("Rastejando");

	}

	@Override
	public void alimentar() {
		System.out.println("Comendo vegetais");

	}

	@Override
	public void emitirSom() {
		System.out.println("Som de réptil");

	}

	public String getCorEscama() {
		return corEscama;
	}

	public void setCorEscama(String corEscama) {
		this.corEscama = corEscama;
	}
}

```
# Principal
```java
package Pkg6;

public class Principal {

	public static void main(String[] args) {
		// Animal n = new Animal();
		Mamifero m = new Mamifero();
		Reptil r = new Reptil();
		Peixe p = new Peixe();
		Ave a = new Ave();

		m.setPeso(35.3f);
		m.setCorPelo("Marrom");
		m.alimentar();
		m.locomover();
		m.emitirSom();

	}

}
```
