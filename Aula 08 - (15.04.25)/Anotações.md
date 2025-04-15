## Correção dos Exercícios
- Na primeira parte da aula, foi corrigido os exercícios 08 e 10 da lista de exercícios da semana passada
- A correção está disponível na pasta da Aula 08

# Herança
## Exemplo 1
Classe Carro
```java
package Exemplo01;

public class Carro {
	protected String nome;
	
	public String getNome() {
		return nome;
	}

	public void setNome(String nome) {
		this.nome = nome;
	}
	
	public void exibeMsg() {
		System.out.println("Estou na classe CARRO \nO nome do Carro é: " +nome);
	}
}
```

Classe Onibus - Essa classe herda tudo que tem na **Classe Carro**
```java
public class Onibus extends Carro { 
	// Esta classe onibus extende carro 
	// Esta classe herda tudo que tem na classe Carro
	// Alt+Shift+S acessa o Source
	
	protected String modelo;

	public String getModelo() {
		return modelo;
	}

	public void setModelo(String modelo) {
		this.modelo = modelo;
	}
}
```

Classe Principal
```java
public class Principal {

	public static void main(String[] args) {
		Carro c = new Carro();
		c.setNome("Fusca");
		c.exibeMsg();
		System.out.println();
		
		Onibus o = new Onibus();
		o.setNome("Marcopolo"); // setNome está na Classe Carro
		o.setModelo("OF-1519"); // setModelo está na Classe Onibus
		
		o.exibeMsg();  // Este método está na calsse Carro!
		
		System.out.println();
		System.out.println("O nome do carro: " +o.getNome());     // getNome está na Classe Carro
		System.out.println("Modelo do onibus: " +o.getModelo());  // getModelo está na Classe Onibus

	}
}
```

## Exemplo 2
Classe Animal
```java
public class Animal {
	protected String nome;
	protected String idade;
	protected String som;
	
	public String getNome() {
		return nome;
	}
	public void setNome(String nome) {
		this.nome = nome;
	}
	public String getIdade() {
		return idade;
	}
	public void setIdade(String idade) {
		this.idade = idade;
	}
	public String getSom() {
		return som;
	}
	public void setSom(String som) {
		this.som = som;
	}
}
```

Classe Cachorro - Herda tudo da Classe Animal
```java
package Exemplo02;

public class Cachorro extends Animal {
	protected String raca;
	
	public String getRaca() {
		return raca;
	}

	public void setRaca(String raca) {
		this.raca = raca;
	}

	public void latir() {
		System.out.println("AU!");
	}
}
```
Classe Principal
```java
public class Principal {

	public static void main(String[] args) {
		Animal a = new Animal();
		Cachorro c = new Cachorro();

		c.setNome("Biscui");
		c.setIdade("14 anos");
		c.setSom("Latido");
		c.latir();

	}

}
```

## Exemplo 3
Classe Pessoa
```java
public class Pessoa {
	protected String nome;
	protected int idade;

	public Pessoa(String nome, int idade) {
		this.nome = nome;
		this.idade = idade;
	}
	
	public void exibeDados() {
		System.out.println("Nome: " + this.nome);
		System.out.println("Idade: " +this.idade);
	}
}
```

Classe PessoaJuridica - Herda tudo da Classe Animal
```java
public class PessoaJuridica extends Pessoa {
	protected String cnpj;
	protected String socio;
	protected String dataAbertura;

	public PessoaJuridica(String nome, int idade, String cnpj, String socio, String dataAbertura) {
		super(nome, idade); // Significa que quando eu instancio PessoJurídica, preciso chamar o construtor
							// da superclasse (PESSOA)
		this.cnpj = cnpj;
		this.socio = socio;
		this.dataAbertura = dataAbertura;
	}

}
```

Classe Principal
```java
public class Principal {

	public static void main(String[] args) {
		
		Pessoa p = new Pessoa("Ricardo", 40);
		p.exibeDados();
		System.out.println();
		
		PessoaJuridica pj = new PessoaJuridica("ABC DC LTDA", 10, "231466984", "Éric", "15/04/2015");
		pj.exibeDados();
		System.out.println("CNPJ: " +pj.cnpj);
		System.out.println("Sócio: " +pj.socio);
		System.out.println("Data de abertura: " +pj.dataAbertura);
	}

}
```
# HERANÇA MULTIPLA
## Exemplo 04
Classe Desenho
```java
public class Desenho {
	protected String nomeAutor;

	public String getNomeAutor() {
		return nomeAutor;
	}

	public void setNomeAutor(String nomeAutor) {
		this.nomeAutor = nomeAutor;
	}
	
}
```

Classe Desenho2d - Herda tudo da Classe Desenho
```java
package Exemplo04HerancaMultipla;

public class Desenho2d extends Desenho {
	protected int largura;
	protected int altura;
	
	public Desenho2d(int largura, int altura) {
		super();
		this.largura = largura;
		this.altura = altura;
	}
}
```

Classe Quadrado - Herda tudo da Classe Desenho e da Classe Desenho2d
```java
package Exemplo04HerancaMultipla;

public class Quadrado extends Desenho2d {
	protected String desc;

	public Quadrado(int largura, int altura, String desc) {
		super(largura, altura);
		this.desc = desc;
	}
	
	public void exibirDados() {
		System.out.println("Nome autor: " +this.nomeAutor);
		System.out.println("Largura: " +this.largura);
		System.out.println("Altura: " +this.altura);
		System.out.println("Descrição: " +this.desc);
	}

}
```

Outro Pacote com a Main principal, herda tudo das classes acima
```java
package Principal;

import Exemplo04HerancaMultipla.Quadrado; // Aqui tem que importar o pacote que estão as classes

public class PrincipalDesenho {

	public static void main(String[] args) {
		Quadrado q = new Quadrado(100, 200, "Quadrado - Ricardo");
		q.setNomeAutor("Ricardo Frohlich");
		q.exibirDados();

	}

}
```
