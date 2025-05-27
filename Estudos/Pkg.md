# ContaBanco
```java
package Pkg;

public class ContaBanco {
	public int numConta;
	protected String tipo;
	private String dono;
	private double saldo;
	private boolean status;

	public void estadoAtual() {
		System.out.println("Conta:" + this.getNumConta());
		System.out.println("Tipo: " + this.getTipo());
		System.out.println("Dono: " + this.getDono());
		System.out.println("Saldo: " + this.getSaldo());
		System.out.println("Status: " + this.getStatus());
		System.out.println();
	}

	public void abrirConta(String tipo) {
		this.setTipo(tipo);
		this.setStatus(true);
		if (tipo == "CC") {
			this.setSaldo(50);
		} else if (tipo == "CP") {
			this.setSaldo(150);
		}
		System.out.println("Conta aberta com sucesso!");
	}

	public void fecharConta() {
		if (this.getSaldo() > 0) {
			System.out.println("Conta não pode ser fechada pois ainda tem dinheiro");
		} else if (this.getSaldo() < 0) {
			System.out.println("Conta não pode ser fechada pois possui débito");
		} else {
			this.setStatus(false);
			System.out.println("Conta fechada com sucesso");
		}
	}

	public void depositar(double valor) {
		if (this.getStatus()) {
			this.setSaldo(this.getSaldo() + valor);
			System.out.println("Depósito realizado na conta de " + this.getDono());
		} else {
			System.out.println("Impssível depositar em uma conta fechada!");
		}
	}

	public void sacar(double valor) {
		if (this.getStatus()) {
			if (this.getSaldo() >= valor) {
				this.setSaldo(this.getSaldo() - valor);
				System.out.println("Saque realizado na conta de " + this.getDono());
			} else {
				System.out.println("Saldo insuficiente para saque");
			}
		} else {
			System.out.println("Impossível sacar de uma conta fechada!");
		}
	}

	public void pagarMensalidade() {
		int valor = 0;
		if (this.getTipo() == "CC") {
			valor = 12;
		} else if (this.getTipo() == "CP") {
			valor = 20;
		}
		if (this.getStatus()) {
			this.setSaldo(getSaldo() - valor);
			System.out.println("Mensalidade paga com sucesso por " + this.getDono());
		} else {
			System.out.println("Impossível pagar uma conta fechada!");
		}
	}

	public ContaBanco() {
		this.setSaldo(0);
		this.setStatus(false);
	}

	public int getNumConta() {
		return numConta;
	}

	public void setNumConta(int numConta) {
		this.numConta = numConta;
	}

	public String getTipo() {
		return tipo;
	}

	public void setTipo(String tipo) {
		this.tipo = tipo;
	}

	public String getDono() {
		return dono;
	}

	public void setDono(String dono) {
		this.dono = dono;
	}

	public double getSaldo() {
		return saldo;
	}

	public void setSaldo(double saldo) {
		this.saldo = saldo;
	}

	public boolean getStatus() {
		return status;
	}

	public void setStatus(boolean status) {
		this.status = status;
	}

}

```
# Principal
```java
package Pkg;

public class Principal {

	public static void main(String[] args) {
		ContaBanco p1 = new ContaBanco();
		p1.setNumConta(1111);
		p1.setDono("Éric");
		p1.abrirConta("CC");
		
		ContaBanco p2 = new ContaBanco();
		p2.setNumConta(2222);
		p2.setDono("Anna");
		p2.abrirConta("CP");
		
		p1.depositar(100);
		p2.depositar(500);
		p2.sacar(100);
		
		p1.sacar(150);
		p1.fecharConta();
		
		p1.estadoAtual();
		p2.estadoAtual();
		

	}

}

```
