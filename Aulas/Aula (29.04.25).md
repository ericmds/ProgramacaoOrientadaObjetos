# Polimorfismo
* Vem do grego
  * poli = muitas
  * morphos = formas
* Permite programar no geral ao invés de "programar no específico"

## Sobresquita de métodos
* Métodos com o mesmo nome, mesmos parâmetros e mesmo tipo de retorno, alterando apenas o comportamento do método
  * Tudo é igual, só muda a implementação

## Sobrecarga
* Métodos com o mesmo nome, com parâmetros diferentes

---
## Exemplo 1
### Classe Animal
```java
package Exemplo1;

public class Animal {
	public String nome;

	public void emitirSom() {
		System.out.println("Animal emitindo som...");
	}
}
```

### Classe Cachorro
```java
package Exemplo1;

public class Cachorro extends Animal{
	public String raca;
	
	@Override
	public void emitirSom() {
		System.out.println("Au au");
	}
}
```

### Classe Capivara
```java
package Exemplo1;

public class Capivara {
	public void emitirSom() {
		System.out.println("Wheek-wheek");
	}
}
```

### Classe Hipopótamo
```java
package Exemplo1;

public class Hipopótamo extends Animal{
	
	public void emitirSom() {
		System.out.println("Piu piu");
	}

}
```

### Classe Passarinho
```java
package Exemplo1;

public class Passarinho extends Animal{

	public void emitirSom() {
		System.out.println("Piu piu");
	}
	
}
```

### Classe Peixe
```java
package Exemplo1;

public class Peixe extends Animal{
	
	public void emitirSom() {
		System.out.println("Glub glub");
	}
}
```

### Classe Principal
```java
package Exemplo1;

public class Principal {

	public static void main(String[] args) {
		System.out.println("Classe animal chamando o construtor Animal");
		Animal a = new Animal();
		a.nome = "Animal 1";
		a.emitirSom();
		
		System.out.println("\nClasse cachorro chamando o costrutor Cachorro");
		Cachorro c = new Cachorro();
		c.nome = "Caramelo";
		c.raca = "SRD";
		c.emitirSom();
		
		System.out.println("\nClasse animal chamando o construtor Cachorro");
		a = new Cachorro();
		a.emitirSom();
		
		System.out.println("\nClasse capivara chamando o construtor Capivara");
		Capivara capinho = new Capivara();
		capinho.emitirSom();
	}

}
```

---

## Exemplo 2
### Classe Pessoa
```java

```
### Classe Programador
```java

```
### Classe Principal
```java

```

---

## Exemplo 3
### Classe Calculadora
```java

```

### Classe Principal
```java

```

---

## Exemplo 4
### Classe Pessoa
```java

```

### Classe Principal
```java

```
