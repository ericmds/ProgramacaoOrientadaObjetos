# Animal
```java
package Pkg7;

public abstract class Animal {
	protected float peso;
	protected int idade;
	protected int membros;

	public abstract void emitirSom();
}

```
# Mamifero
```java
package Pkg7;

public class Mamifero extends Animal {
	private String corPelo;

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
# Cachorro
```java
package Pkg7;

public class Cachorro extends Lobo {
	@Override
	public void emitirSom() {
		System.out.println("Au au au au");
	}

	public void reagir(String frase) {
		if (frase == "Toma Comiad" || frase == "Olá") {
			System.out.println("Abanar e latir");
		} else {
			System.out.println("Rosnar");
		}
	}

	public void reagir(int hora, int min) {
		if (hora < 12) {
			System.out.println("Abanar");
		} else if (hora >= 18) {
			System.out.println("Ignorar");
		} else {
			System.out.println("Abanar e latir");
		}
	}

	public void reagir(boolean dono) {
		if (dono) {
			System.out.println("Abanar");
		} else {
			System.out.println("Abanar e latir");
		}
	}

	public void reagir(int idade, float peso) {
		if (idade < 5) {
			if (peso < 10) {
				System.out.println("Abanar");
			} else {
				System.out.println("Latir");
			}
		} else {
			if (peso < 10) {
				System.out.println("Rosnar");
			} else {
				System.out.println("Ignorar");
			}
		}
	}
}

```
# Lobo
```java
package Pkg7;

public class Lobo extends Mamifero {
	@Override
	public void emitirSom() {
		System.out.println("Auuuuuu");
	}

}

```
# Principal
```java
package Pkg7;

public class Principal {

	public static void main(String[] args) {
		Cachorro c = new Cachorro();

		c.reagir("Olá");
		c.reagir("Vai apanhar!");
		c.reagir(11, 45);
		c.reagir(19, 00);
		c.reagir(true);
		c.reagir(2, 12.5f);
		c.reagir(17, 4.5f);
		
	}

}

```
