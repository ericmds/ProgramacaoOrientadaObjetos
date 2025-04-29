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
package Exemplo2;

public class Pessoa {
	
	public void trabalhar() {
		System.out.println("Trabalhando");
	}
}
```
### Classe Programador
```java
package Exemplo2;

public class Programador extends Pessoa{
	public void trabalhar() {
		System.out.println("Programando");
	}

}
```
### Classe Principal
```java
package Exemplo2;

public class Principal {
	public static void main(String[] agrs) {
		Pessoa pe = new Pessoa();
		pe.trabalhar();
		
		Programador pro = new Programador();
		pro.trabalhar();
	}
}
```

---

## Exemplo 3
### Classe Calculadora
```java
package Exemplo3;

public class Calculadora {
	public int Somar(int x, int y) {
		System.out.println("\nUsando int com 2 variaveis");
		return x + y;
	}

	public int Somar(int x, int y, int z) {
		System.out.println("\nUsando int com 3 variaveis");
		return x + y + z;
	}
	
	public double Somar (double x, double y) {
		System.out.println("\nUsando double com 2 variaveis");
		return x + y;
	}
	
	public int Multiplica(int x, int y) {
		System.out.println("\nUsando double com 2 variais");
		return x * y;
	}
	
	public double Multiplica(double x, double y) {
		System.out.println("\nUsando double com 2 variais");
		return x * y;
	}
}
```

### Classe Principal
```java
package Exemplo3;

public class Principal {

	public static void main(String[] args) {
		Calculadora c = new Calculadora();
		
		int resultado1 = c.Somar(5, 7);
		System.out.println("Resultado 1: " + resultado1);
		
		int resultado2 = c.Somar(5, 7, 5);
		System.out.println("Resultado 1: " + resultado2);
		
		double resultado3 = c.Somar(3.5, 7.0);
		System.out.println("Resultado 3: " + resultado3);
		
		double resultado4 = c.Somar(3, 7);
		System.out.println("Resultado 4: " + resultado4);
		
		int resultado5 = c.Multiplica(5, 5);
		System.out.println("Resultado 5: " + resultado5);
		
		double resultado6 = c.Multiplica(2.5, 4.5);
		System.out.println("Resultado 5: " + resultado6);
	}

}
```

---

## Exemplo 4
### Classe Pessoa
```java
package Exemplo4;

public class Pessoa {
	public void dizerOla() {
		System.out.println("Olá");
	}
	
	public void dizerOla(String nome) {
		System.out.println("Olá, <"+nome+">!.");
	}
}
```

### Classe Principal
```java
package Exemplo4;

public class Principal {

	public static void main(String[] args) {
		Pessoa p = new Pessoa();
		
		p.dizerOla();
		p.dizerOla("Eric");

	}

}
```
