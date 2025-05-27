# 1) Crie uma classe abstrata chamada Conta com os atributos Saldo e Limite. Crie também métodos abstratos para Depositar e Sacar.
# 2) Faça implementação concreta desta classe com os métodos Depositar e sacar
# 3) Faça as implementações dos métodos para uma ContaInvestimento e ContaCorrente e apresente mensagens na tela.
## Conta
```java
package Exercicio01_02_03;

public abstract class Conta {
	protected double saldo;
	protected double limite;

	public Conta(double saldo, double limite) {
		this.saldo = saldo;
		this.limite = limite;
	}

	public abstract void depositar(double valor);

	public abstract void sacar(double valor);

	public double getSaldo() {
		return saldo;
	}

	public double getLimite() {
		return limite;
	}
}

```
## ContaBancaria
```java
package Exercicio01_02_03;

public class ContaBancaria extends Conta {

	public ContaBancaria(double saldo, double limite) {
		super(saldo, limite);
	}

	@Override
	public void depositar(double valor) {
		saldo += valor;
		System.out.println("Depósito de R$" + valor + " realizado. Novo saldo: R$" + saldo);
	}

	@Override
	public void sacar(double valor) {
		if (valor <= saldo + limite) {
			saldo -= valor;
			System.out.println("Saque de R$" + valor + " realizado. Novo saldo: R$" + saldo);
		} else {
			System.out.println("Saldo insuficiente para saque de R$" + valor);
		}
	}
}

```
## ContaCorrente
```java
package Exercicio01_02_03;

public class ContaCorrente extends Conta {

    public ContaCorrente(double saldo, double limite) {
        super(saldo, limite);
    }

    @Override
    public void depositar(double valor) {
        saldo += valor;
        System.out.println("Conta Corrente: Depósito de R$" + valor + " realizado. Saldo atual: R$" + saldo);
    }

    @Override
    public void sacar(double valor) {
        if (valor <= saldo + limite) {
            saldo -= valor;
            System.out.println("Conta Corrente: Saque de R$" + valor + " realizado. Saldo atual: R$" + saldo);
        } else {
            System.out.println("Conta Corrente: Saldo insuficiente para saque de R$" + valor);
        }
    }
}

```
## ContaInvestimento
```java
package Exercicio01_02_03;

public class ContaInvestimento extends Conta {

    public ContaInvestimento(double saldo, double limite) {
        super(saldo, limite);
    }

    @Override
    public void depositar(double valor) {
        saldo += valor * 1.01;
        System.out.println("Conta Investimento: Depósito com rendimento de 1%. Novo saldo: R$" + saldo);
    }

    @Override
    public void sacar(double valor) {
        if (valor <= saldo) {
            saldo -= valor;
            System.out.println("Conta Investimento: Saque de R$" + valor + " realizado. Saldo atual: R$" + saldo);
        } else {
            System.out.println("Conta Investimento: Saldo insuficiente para saque de R$" + valor);
        }
    }
}

```
## Principal
```java
package Exercicio01_02_03;

public class Principal {
	public static void main(String[] args) {

		Conta conta1 = new ContaCorrente(1000, 500);
		Conta conta2 = new ContaInvestimento(2000, 0);

		conta1.depositar(200);
		conta1.sacar(1500);
		conta1.sacar(300);

		System.out.println();

		conta2.depositar(1000);
		conta2.sacar(500);
		conta2.sacar(3000);

	}
}

```
