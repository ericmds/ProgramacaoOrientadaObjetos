# ✦ Exercícios sobre <ins>Tratamento de exceções</ins>
## 1 - Escreva um programa que solicita ao usuário para digitar um número inteiro e exiba a raiz quadrada desse número. Certifique-se de que o programa trate adequadamente as exceções se o usuário digitar um valor inválido, por exemplo, ler um char ou string.Faça o tratamento de exceções em uma calculadora.
```
package Exercícios;

import java.util.Scanner;

public class Exercício01 {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);
		int numero;
		double raiz;
		
		System.out.print("Digite um número inteiro: ");
		
		
		try {
			numero = teclado.nextInt();
			raiz = Math.sqrt(numero);
			System.out.println("Raiz quadrada de " +numero+ " = " +raiz);
		} catch (Exception e){
			System.out.println("Erro encontrado!");
			System.out.println("Exeção: " +e.toString());	
		}
		System.out.println("Seguindo execução do progama...");
		
		teclado.close();
	}
	
}
```
## 2 – Faça o tratamento de exceções em uma calculadora.
```
package Exercícios;

import java.util.Scanner;

public class Exercicio02 {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);
		int numero1, numero2, resultado;
		
		System.out.println("Informe o valor do primeiro numero: ");
		numero1 = teclado.nextInt();
		System.out.println("Informe o valor do segundo número: ");
		numero2 = teclado.nextInt();
		
		try {
			System.out.println(numero1/numero2);
		} catch (Exception e){
			System.out.println("Exceção: " + e.getMessage());
			System.out.println("Exceção: " + e.toString());
		}
		
		
		teclado.close();
	}
}
```
## 3 – Faça o tratamento de exceções em conversões de valores lidos pelo teclado. Por exemplo, ao ler uma string e converter ela para double.

## 4 – Pesquise quais são as Exceções existentes que já possuem tratamento e explique brevemente como cada uma funciona. Teste duas exceções.
