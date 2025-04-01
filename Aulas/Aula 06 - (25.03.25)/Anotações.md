# ENCAPSULAMENTO
* O encapsulamento é implementado usando modificadores de acesso, que são palavras-chave que determinam o nível de acesso aos membros de uma classe (atributos e métodos)

* Os modificadores de acesso em java são:
  * public
  * private
  * protected
  * default
    
# Exemplo 01
Classe pessoa
```java
package Exemplo_01;

public class Pessoa {
	
	private String nome; // public String nome;
	private int idade; // public int idade;
	public String cpf;
	
	public void apresentaDados() {
		System.out.println("Nome: " +nome);
		System.out.println("Idade: " +idade);
		System.out.println("CPF: " +cpf);
	}

	// Lembrete: Construtor não retorna nada
	public Pessoa(String nome, int idade, String cpf) {
		this.nome = nome;
		this.idade = idade;
		this.cpf = cpf;
	}

	// get = para buscar dados
	public int getIdade() {
		return idade;
	}
	
	// set = para atribuir dados
	public void setIdade(int idade) {
		if(idade >= 0) {
			this.idade = idade;
		} else
			System.out.println("A idade não pode ser negativa");
	}
	
	public String getCpf() {
		return this.cpf;
	}

	public String getNome() {
		return nome;
	}

	public void setNome(String nome) {
		this.nome = nome;
	}
}

```

Classe Principal
```java
package Exemplo_01;

public class Principal {

	public static void main(String[] args) {
		Pessoa p = new Pessoa("Éric", 24, "123.456.789.00");
		
		/*p.nome = "Ricardo";
		p.idade = 40; */
		
		// p.atribuiDados("Éric", 24);
		// System.out.println("Nome: " +p.nome);
		// System.out.println("Idade: " +p.idade);
		
		p.apresentaDados();
		
		int idade, ano;
		idade = p.getIdade(); // Retorna idade
		
		//ano = 2025-p.idade;
		
		ano = 2025 - idade;
		System.out.println("Ano de nascimento: " +ano);
		
		p.setIdade(25);
		p.apresentaDados();
		
		p.setNome("ANNA");
		p.apresentaDados();

	}
}
```
