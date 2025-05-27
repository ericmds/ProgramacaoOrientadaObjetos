# Pessoa
```java
package Pkg4;

public class Pessoa {
	private String nome;
	private int idade;
	private String sexo;

	public void fazerAniversario() {
		this.idade ++;
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
# Aluno
```java
package Pkg4;

public class Aluno extends Pessoa{
	private int mat;
	private String curso;

	public void cancelarMatricula() {
		System.out.println("Matrícula será cancelada!");
	}

	public int getMat() {
		return mat;
	}

	public void setMat(int mat) {
		this.mat = mat;
	}

	public String getCurso() {
		return curso;
	}

	public void setCurso(String curso) {
		this.curso = curso;
	}

}

```
# Funcionario
```java
package Pkg4;

public class Funcionario extends Pessoa {
	private String setor;
	private boolean trabalhando;

	public void mudaTrabalho() {
		this.trabalhando = !this.trabalhando;
	}

	public String getSetor() {
		return setor;
	}

	public void setSetor(String setor) {
		this.setor = setor;
	}

	public boolean isTrabalhando() {
		return trabalhando;
	}

	public void setTrabalhando(boolean trabalhando) {
		this.trabalhando = trabalhando;
	}

}

```
# Professor
```java
package Pkg4;

public class Professor extends Pessoa {
	private String especialidade;
	private float salario;

	public void receberAumento(float aumento) {
		this.salario += aumento;
	}

	public String getEspecialidade() {
		return especialidade;
	}

	public void setEspecialidade(String especialidade) {
		this.especialidade = especialidade;
	}

	public float getSalario() {
		return salario;
	}

	public void setSalario(float salario) {
		this.salario = salario;
	}

}

```
# Principal
```java
package Pkg4;

public class Principal {

	public static void main(String[] args) {
		Pessoa p1 = new Pessoa();
		Aluno p2 = new Aluno();
		Professor p3 = new Professor();
		Funcionario p4 = new Funcionario();

		p1.setNome("Éric");
		p2.setNome("Anna");
		p3.setNome("Laís");
		p4.setNome("Gael");
		
		p1.setSexo("M");
		p3.setSexo("F");
		p2.setIdade(23);

		p2.setCurso("Informática");
		p3.setSalario(2500.75f);
		p4.setSetor("Estoque");
		
		System.out.println(p1.toString());
		System.out.println(p2.toString());
		System.out.println(p3.toString());
		System.out.println(p4.toString());
	}

}

```
