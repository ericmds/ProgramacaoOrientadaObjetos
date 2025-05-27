# Pessoa
```java
package Pkg5;

public abstract class Pessoa {
	private String nome;
	private int idade;
	private String sexo;

	public void fazerAniversario() {
		this.idade++;
	}

	public String getNome() {
		return nome;
	}

	public void setNome(String nome) {
		this.nome = nome;
	}

	public int getIdade() {
		return idade;
	}

	public void setIdade(int idade) {
		this.idade = idade;
	}

	public String getSexo() {
		return sexo;
	}

	public void setSexo(String sexo) {
		this.sexo = sexo;
	}

	@Override
	public String toString() {
		return "Pessoa [nome=" + nome + ", idade=" + idade + ", sexo=" + sexo + "]";
	}

}

```
# Visitante
```java
package Pkg5;

public class Visitante extends Pessoa {

}

```
# Aluno
```java
package Pkg5;

public class Aluno extends Pessoa {
	private int matricula;
	private String curso;

	public void pagarMensalidade() {
		System.out.println("Pagando mensalidade do aluno " + this.getNome());
	}

	public int getMatricula() {
		return matricula;
	}

	public void setMatricula(int matricula) {
		this.matricula = matricula;
	}

	public String getCurso() {
		return curso;
	}

	public void setCurso(String curso) {
		this.curso = curso;
	}

}

```
# Bolsista
```java
package Pkg5;

public class Bolsista extends Aluno {
	private float bolsa;

	public void renovarBolsa() {
		System.out.println("Renovando a bolsa de " + this.getNome());
	}

	@Override
	public void pagarMensalidade() {
		System.out.println(this.getNome() + " é bolsista! Pagamento facilitado");
	}

	public float getBolsa() {
		return bolsa;
	}

	public void setBolsa(float bolsa) {
		this.bolsa = bolsa;
	}

}

```
# Principal
```java
package Pkg5;

public class Principal {

	public static void main(String[] args) {
		Visitante v1 = new Visitante();
		v1.setNome("Éric");
		v1.setIdade(24);
		v1.setSexo("M");
		System.out.println(v1.toString() + "\n");
		
		Aluno a1 = new Aluno();
		a1.setNome("Anna");
		a1.setIdade(23);
		a1.setSexo("F");
		a1.setMatricula(1234);
		a1.setCurso("Fisio");
		a1.pagarMensalidade();
		
		Bolsista b1 = new Bolsista();
		b1.setNome("Claiton");
		b1.setIdade(54);
		b1.setSexo("M");
		b1.setMatricula(5678);
		b1.setCurso("Adm");
		b1.pagarMensalidade();

	}

}

```
