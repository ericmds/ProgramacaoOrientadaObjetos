# Exercícios - Herança e polimorfismo 
## 02) Crie uma classe Produto com um método desconto(). Em seguida, crie uma classeProdutoComDesconto que herda da classe Produto e sobrescreve o método desconto() paracalcular o desconto do produto com base em um valor predefinido e imprimir o preço comdesconto.
### Classe Produto
```java
package Exercicio02;

public class Produto {
	protected String produto;
	protected double preco;

	public Produto(String produto, double preco) {
		this.produto = produto;
		this.preco = preco;
	}

	public String getProduto() {
		return produto;
	}

	public void setProduto(String produto) {
		this.produto = produto;
	}

	public double getPreco() {
		return preco;
	}

	public void setPreco(double preco) {
		this.preco = preco;
	}

	public void desconto() {
		System.out.println("Produto: " + produto);
		System.out.printf("Preço original: R$%.2f", preco);
	}
}
```
### Classe ProdutoComDesconto
```java
package Exercicio02;

public class ProdutoComDesconto extends Produto {
	protected double quantidadeDesconto;

	public ProdutoComDesconto(String produto, double preco, double quantidadeDesconto) {
		super(produto, preco);
		this.quantidadeDesconto = quantidadeDesconto;
	}

	public void desconto() {
		double valorDesconto = preco * (quantidadeDesconto / 100);
		double produtoDesconto = preco - valorDesconto;

		System.out.println("Produto: " + produto);
		System.out.println("Desconto: " + valorDesconto);
		System.out.println(produto + " com desconto de " + quantidadeDesconto + "% = R$" + produtoDesconto);
	}
}
```
### Classe Principal
```java
package Exercicio02;

import java.util.Scanner;

public class Principal {

	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);

		Produto p = new Produto("Fusca", 7699.90);
		p.desconto();

		System.out.println("\n");

		ProdutoComDesconto pd = new ProdutoComDesconto("Fusca", 7699.90, 50);
		pd.desconto();

		teclado.close();
	}
}
```

## 03) Crie uma classe Funcionario com um método calcularSalario(). Em seguida, crie uma classeGerente que herda da classe Funcionario e sobrescreve o método calcularSalario() para calcularo salário do gerente com base em um bônus e imprimir o resultado.
### Classe
```java

```

## 04) Crie uma classe ContaBancaria com um método depositar(double valor) que adiciona o valorpassado como parâmetro ao saldo da conta. Sobrecarregue o método depositar() para aceitar umobjeto Cheque e adicionar o valor do cheque ao saldo da conta.
### Classe
```java

```

## 05) Crie uma classe Produto com um método calcularPrecoFinal(double preco) que retorna opreço final do produto com base no preço passado como parâmetro. Sobrecarregue o métodocalcularPrecoFinal() para aceitar um objeto Cliente e calcular o preço final do produto com base no desconto do cliente.
### Classe
```java

```

## 06) Crie uma classe base Funcionario com atributos como nome e salario. Deriveclasses específicas como Gerente e Desenvolvedor. Gerente possui um bônus anual,enquanto Desenvolvedor tem horas extras.
* Implemente métodos sobrecarregados aumentarSalario que aumentam o saláriobaseado em diferentes critérios (porcentagem fixa para todos e uma porcentagemadicional para Gerente que considera o bônus).
* Sobrescreva o método toString para refletir informações específicas de cada tipode funcionário.
* Crie um array de Funcionario que inclua Gerente e Desenvolvedor, e demonstre a aplicação dos aumentos de salário e a impressão das informações.
### Classe
```java

```

## 07) Crie uma classe Notificacao com um método enviar. Derive classes como NotificacaoEmail e NotificacaoApp que extendem Notificacao.
* Sobrecarregue o método enviar em NotificacaoEmail para aceitar um ou mais destinatários.
* Sobrescreva o método enviar em cada classe derivada para implementar a lógica específica de envio.
* Demonstre o envio de diferentes tipos de notificações usando objetos das classes derivadas.
### Classe
```java

```

## 08) Crie uma classe Reserva com métodos para adicionar e cancelar reservas. Derive classes como ReservaDeHotel e ReservaDeVoo da classe Reserva.
* Sobrecarregue o método adicionar em ReservaDeVoo para aceitar diferentes tipos de classes (econômica, executiva).
* Sobrescreva o método cancelar em ambas as classes derivadas para tratar políticas de cancelamento específicas.
* Demonstre como criar e cancelar diferentes tipos de reservas usando polimorfismo.
### Classe
```java

```

## 09) Crie uma classe Produto com atributos nome, preco e quantidade. Crie uma lista de produtos e adicione alguns produtos nessa lista. Em seguida, percorra a lista e imprima os dados de cada produto.
### Classe
```java

```

## 10) Crie uma classe Aluno com atributos nome, nota1 e nota2. Crie uma lista de alunos e adicione alguns alunos nessa lista. Em seguida, percorra a lista e calcule a média de cada aluno. Se a média for maior ou igual a 6, imprima que o aluno foi aprovado. Caso contrário, imprima que o aluno foi reprovado.
### Classe
```java

```

## 11) Crie uma classe Pessoa com atributos nome, idade e sexo. Crie uma lista de pessoas e adicione algumas pessoas nessa lista. Em seguida, crie um método que recebe uma lista de pessoas e retorna a quantidade de mulheres. Por fim, chame esse método passando a lista de pessoas e imprima a quantidade de mulheres.
### Classe
```java

```

## 12) Crie uma classe Livro com atributos titulo, autor e ano. Crie uma lista de livros e adicione alguns livros nessa lista. Em seguida, ordene a lista de livros pelo ano de lançamento e imprima os dados de cada livro.
### Classe
```java

```

## 13) Crie uma classe Conta com atributos numero, titular e saldo. Crie uma lista de contas e adicione algumas contas nessa lista. Em seguida, crie um método que recebe uma lista de contas e retorna a conta com o maior saldo. Por fim, chame esse método passando a lista de contas e imprima os dados da conta com o maior saldo.
### Classe
```java

```
