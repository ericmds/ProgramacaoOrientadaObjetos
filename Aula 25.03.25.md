# Correção Exercício - 01
## Classe Disciplina
```
package Correcao_01;

public class Disciplina {
	public String nome;
	public int cargaHoraria;
	public String nomeProfessor;
	
	public void atribuiNome(String nomeDisciplina) {
		nome = nomeDisciplina;
	}
	
	public String recuperarNome() {
		return nome;
	}
	
	public void atribuirCargaHoraria(int carga) {
		cargaHoraria = carga;
	}
	
	public int recuperarCargaHoraria() {
		return cargaHoraria;
	}
	
	public void atribuirNomeProfessor(String nomeProf) {
		nomeProfessor = nomeProf;
	}
	
	public String recuperarNomeProfessor() {
		return nomeProfessor;
	}
}

```

## Classe Principal
```
package Correcao_01;

public class Principal {

	public static void main(String[] args) {
		Disciplina d = new Disciplina();
		d.atribuiNome("Programação Orientada à Objetos");
		//d.nome = "Programação orientada á obetos";
		//System.out.println("Nome: "+d.nome);
		String nomeDisciplina;
		nomeDisciplina = d.recuperarNome();
		System.out.println("Nome recuperado: "+nomeDisciplina);
		d.atribuirCargaHoraria(50);
		
		int carga;
		carga = d.recuperarCargaHoraria();
		System.out.println("Carga horária: "+carga);
		
		d.atribuirNomeProfessor("Girafales");
		System.out.println("Nome do professor: "+d.recuperarNomeProfessor());

	}

}
```

#Aula

## Exemplo 1
```
package Exemplo_01;

public class Exemplo01 {
	public static void main(String[] args) {
		//Exemplo 1: Tentando acessar um elemento fora do índice de um array
		
		int[] numeros = {1, 2 ,3};
		System.out.println(numeros[3]); // ArrayIndexOutOfBoundsException

	}
}

```

## Exemplo 2
```
package Exemplo_02;

public class Exemplo02 {

	public static void main(String[] args) {
		// Exemplo 2: Divisão por zero
		
		int a = 10;
		int b = 0;
		System.out.println(a/b); // ArithmeticException

	}

}
```

##Exemplo 3
```
package Exemplo_03;

public class Exemplo03 {
	public static void main(String[] args) {
		// Exemplo 3: Tentando converter uma String em um número
		
		String numero = "abc";
		int valor = Integer.parseInt(numero); // NumberFormatException
	}

}
```
