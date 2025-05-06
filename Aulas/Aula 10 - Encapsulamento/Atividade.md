# Exercício 3
## Principal com repetição
```java
package Exercicio03;

import java.util.Scanner;

public class Principal {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);

		String mensagem;
		int repeticoes;
		int opcao;

		Pessoa p = new Pessoa();

		while (true) {
			System.out.println("\nEscolha uma opção:");
			System.out.println("1 - Falar uma mensagem");
			System.out.println("2 - Falar uma mensagem repetida");
			System.out.println("0 - Sair");
			System.out.print("Opção: ");
			opcao = teclado.nextInt();
			teclado.nextLine();

			switch (opcao) {
			case 1:
				System.out.print("Digite uma mensagem: ");
				mensagem = teclado.nextLine();
				p.falar(mensagem);
				break;

			case 2:
				System.out.print("Digite uma mensagem: ");
				mensagem = teclado.nextLine();
				System.out.print("Digite o número de repetições: ");
				repeticoes = teclado.nextInt();
				teclado.nextLine();
				p.falar(mensagem, repeticoes);
				break;

			case 0:
				System.out.println("Encerrando o programa...");
				teclado.close();
				return;

			default:
				System.out.println("Opção inválida");
				break;
			}
		}
	}
}
```
