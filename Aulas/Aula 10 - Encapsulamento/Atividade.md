# EXERCÍCIO 1
## Classe FormaGeometrica
```java
package Exercicio01;

public class FormaGeometrica {
	public double base;
	public double altura;

	public FormaGeometrica(double base, double altura) {
		this.base = base;
		this.altura = altura;
	}

	public FormaGeometrica() {
	}

	public void calcularArea() {
		System.out.println("Método qualquer para calcular a área");
	}
}
```

## Classe Triangulo
```java
package Exercicio01;

public class Triangulo extends FormaGeometrica {

	public Triangulo(double base, double altura) {
		super(base, altura);
	}

	public void calcularArea() {
		System.out.println("Método para calcular a área do triângulo");
		double area = (base * altura) / 2;
		System.out.println("Área do triângulo: " + area);
	}
}
```

## Classe Principal
```java
package Exercicio01;

public class Principal {

	public static void main(String[] args) {
		FormaGeometrica f = new FormaGeometrica();
		f.calcularArea();

		System.out.println();

		Triangulo t = new Triangulo(10, 5);
		t.calcularArea();
	}
}
```

---

# EXERCÍCIO 2
## Classe ContaBancaria
```java
package Exercicio02;

public class ContaBancaria {
	public double saldo;

	public ContaBancaria(double saldo) {
		this.saldo = saldo;
	}

	public ContaBancaria() {

	}

	public void calcularSaldo() {
		System.out.println("Calculando saldo da sua conta bancária...");
	}
}
```

## Classe ContaCorrente
```java
package Exercicio02;

public class ContaCorrente extends ContaBancaria {

	public ContaCorrente(double saldo) {
		super(saldo);
	}

	public void calcularSaldo() {
		System.out.println("Calculando saldo da sua conta corrente...");
		System.out.println("O saldo da sua conta corrente é de R$" + saldo);
	}
}
```

## Classe Principal
```java
package Exercicio02;

public class Principal {

	public static void main(String[] args) {
		ContaBancaria cb = new ContaBancaria();
		cb.calcularSaldo();

		System.out.println();

		ContaCorrente cc = new ContaCorrente(4523.69);
		cc.calcularSaldo();
	}
}
```

---

# EXERCÍCIO 3
## Classe Pessoa
```java
package Exercicio03;

public class Pessoa {

	public void falar(String mensagem) {
		System.out.println("Exibindo mensagem informada...");
		System.out.println("Mensagem: " + mensagem);
	}

	public void falar(String mensagem, int repeticoes) {
		System.out.println("Exibindo mensagem informada com repetições...");
		for (int i = 0; i < repeticoes; i++) {
			System.out.println("Repetição " + (i + 1) + " | Mensagem: " + mensagem);
		}
	}
}
```
## Classe Principal
```java
package Exercicio03;

import java.util.Scanner;

public class Principal {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);

		String mensagem;
		int repeticoes;

		Pessoa p = new Pessoa();
		System.out.print("Digite uma mensagem: ");
		mensagem = teclado.nextLine();
		p.falar(mensagem);

		System.out.print("\nDigite uma mensagem: ");
		mensagem = teclado.nextLine();
		System.out.print("Digite o número de repetições: ");
		repeticoes = teclado.nextInt();
		p.falar(mensagem, repeticoes);

		teclado.close();
	}
}
```
## Classe Principal (Com repetição)
```java
package Exercicio03;

import java.util.Scanner;

public class Principal {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);

		String mensagem;
		int repeticoes;
		int opcao;

		Pessoa p = new Pessoa();

		while (true) {
			System.out.println("\nEscolha uma opção:");
			System.out.println("1 - Falar uma mensagem");
			System.out.println("2 - Falar uma mensagem repetida");
			System.out.println("0 - Sair");
			System.out.print("Opção: ");
			opcao = teclado.nextInt();
			teclado.nextLine();

			switch (opcao) {
			case 1:
				System.out.print("Digite uma mensagem: ");
				mensagem = teclado.nextLine();
				p.falar(mensagem);
				break;

			case 2:
				System.out.print("Digite uma mensagem: ");
				mensagem = teclado.nextLine();
				System.out.print("Digite o número de repetições: ");
				repeticoes = teclado.nextInt();
				teclado.nextLine();
				p.falar(mensagem, repeticoes);
				break;

			case 0:
				System.out.println("Encerrando o programa...");
				teclado.close();
				return;

			default:
				System.out.println("Opção inválida");
				break;
			}
		}
	}
}
```
---

# EXERCÍCIO 4
## Classe Casa
```java
package Exercicio04;

public class Casa {
	public double preco;

	public double calcularPreco(int tamanho, double metroQuadrado) {
		preco = tamanho * metroQuadrado;
		return preco;
	}

	public double calcularPreco(int tamanho, double metroQuadrado, int quantidadeQuartos, double precoQuarto) {
		preco = (tamanho * metroQuadrado) + (quantidadeQuartos * precoQuarto);
		return preco;
	}
}
```

## Classe Principal
```java
package Exercicio04;

public class Principal {

	public static void main(String[] args) {
		Casa c = new Casa();

		System.out.println("Preço da casa com base no tamanho em metros quadrados");
		double preco1 = c.calcularPreco(100, 950);
		System.out.println("R$" + preco1);

		System.out.println("\nPreço da casa com base no tamanho e no número de quartos");
		double preco2 = c.calcularPreco(100, 950, 3, 10000);
		System.out.println("R$" + preco2);
	}
}
```
