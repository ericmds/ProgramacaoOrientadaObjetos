# 6) Crie uma classe abstrata chamada Funcionario com os atributos Nome e Salário. Crie também um método abstrato chamado CalcularSalario. Crie duas classes que herdam de Funcionario, uma chamada Gerente e outra chamada Vendedor, que implementam o método CalcularSalario.

## Funcionario
```java
package Exercicio06;

public abstract class Funcionario {
	protected String nome;
	protected double salario;

	public Funcionario(String nome, double salario) {
		this.nome = nome;
		this.salario = salario;
	}

	public abstract double calcularSalario();
}

```
## Gerente
```java
package Exercicio06;

public class Gerente extends Funcionario {
    private double bonus;

    public Gerente(String nome, double salario, double bonus) {
        super(nome, salario);
        this.bonus = bonus;
    }

    @Override
    public double calcularSalario() {
        return salario + bonus;
    }
}

```
## Vendedor
```java
package Exercicio06;

public class Vendedor extends Funcionario {
	private double comissao;

	public Vendedor(String nome, double salario, double comissao) {
		super(nome, salario);
		this.comissao = comissao;
	}

	@Override
	public double calcularSalario() {
		return salario + comissao;
	}
}

```
## Principal
```java
package Exercicio06;

public class Principal {
	public static void main(String[] args) {

		Funcionario gerente = new Gerente("Éric", 5000.0, 2000.0);
		Funcionario vendedor = new Vendedor("Anna", 3000.0, 1500.0);

		System.out.println("Salário do Gerente " + gerente.nome + ": R$ " + gerente.calcularSalario());
		System.out.println("Salário do Vendedor " + vendedor.nome + ": R$ " + vendedor.calcularSalario());

	}
}

```
