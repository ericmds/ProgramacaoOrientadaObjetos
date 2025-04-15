# Correção de exercícios
## Exercício 08
Classe Usuario
```java
package Correcao08;

public class Usuario {
	private String nomeUsuario;
	private String senha;
	private boolean logado; // inicialmente false
	
	public Usuario(String nomeUsuario, String senha) {
		this.nomeUsuario = nomeUsuario;
		this.senha = senha;
		logado = false;
	}

	public String getNomeUsuario() {
		return nomeUsuario;
	}

	public void setNomeUsuario(String nomeUsuario) {
		this.nomeUsuario = nomeUsuario;
	}

	public String getSenha() {
		return senha;
	}

	public void setSenha(String senha) {
		this.senha = senha;
	}
	
	public boolean isLogado() {
		return logado;
	}
	
	public void login(String usuario, String senha) {
		if((usuario.equals(this.nomeUsuario)) && (senha.equals(this.senha))) {
			this.logado = true;
			System.out.println("Mensagem do Sistema: Login efetuado com sucesso!");
		} else {
			System.out.println("Mensagem do Sistema: Login não efetuado");
		}
	}
	
	public void logout() {
		this.logado = false;
		System.out.println("Saindo do sistema...");
	}
	
	public void exibirStatus() {
		System.out.println("Usuário: " + this.nomeUsuario);
	}
	
}
```

Classe Principal
```java
package Correcao08;

import java.util.Scanner;

public class Principal {
	public static void main (String[] args) {
		Scanner teclado = new Scanner(System.in);
		Usuario u = new Usuario ("ricardo", "102030");
		
		System.out.print("Digite o usuário: ");
		String usuario = teclado.nextLine();
		System.out.print("Digite a senha: ");
		String senha = teclado.nextLine();
		
		System.out.println("Tentando login no sistema...");
		u.login(usuario, senha);
		
		u.exibirStatus();
		u.logout();
		u.exibirStatus();
		
		teclado.close();
	}
}
```

## Exercício 10
Classe Tarefa
```java
package Correcao10;

public class Tarefa {
	private String descricao;
	private boolean concluida;
	
	public Tarefa(String descricao) {
		this.descricao = descricao;
		this.concluida = false;
	}
	
	public void concluirTarefa() {
		this.concluida = true;
		System.out.println("Mensagem do sistema: Tarefa concluida!");
	}
	
	public void exibirTarefa() {
		System.out.print("Tarefa " +this.descricao);
		if(this.concluida)  {
			System.out.println(" Concluida!");
		} else { 
			System.out.println(" Não concluida!");
		}
	}
}
```

Classe Principal
```java
package Correcao10;

import java.util.Scanner;

public class Principal {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);
		Tarefa[] tarefas = new Tarefa[3];
		
		for(int i=0; i<3; i++) {
			System.out.println("Digite a descrição da tarefa " +i);
			String descricao = teclado.nextLine();
			tarefas[i] = new Tarefa(descricao);
		}

		tarefas[1].concluirTarefa();
		
		for(int i=0; i<3; i++) {
			tarefas[i].exibirTarefa();
		}
			
		teclado.close();
	}
}
```
