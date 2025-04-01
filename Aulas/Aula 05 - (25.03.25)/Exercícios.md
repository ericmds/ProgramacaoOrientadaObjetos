# ✦ Exercícios sobre <ins>Tratamento de exceções</ins>
## 1 - Escreva um programa que solicita ao usuário para digitar um número inteiro e exiba a raiz quadrada desse número. Certifique-se de que o programa trate adequadamente as exceções se o usuário digitar um valor inválido, por exemplo, ler um char ou string.
```java
package Exercicio_01; // ÉRIC MARTINS DA SILVA
/* 1 - Escreva um programa que solicita ao usuário para digitar um número inteiro e exiba a raiz quadrada desse número. Certifique-se de que o programa
trate adequadamente as exceções se o usuário digitar um valor inválido, por exemplo, ler um char ou string.*/

import java.util.InputMismatchException;
import java.util.Scanner;

public class Principal_01 {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);
		int numero, opcao = 0;
		double raiz;
		
		
		do {
			try {
				System.out.print("Digite um número inteiro: ");
				numero = teclado.nextInt();
				
				raiz = Math.sqrt(numero);
				System.out.println("Raiz quadrada de " +numero+ " = " +raiz);
				
				System.out.println("\n1 - Continuar | 2 - Encerrar");
				System.out.print("Escolha uma opcao: ");
				opcao = teclado.nextInt();
				System.out.println();
				
			} catch (InputMismatchException e) {
				System.out.println("\nErro encontrado! Digite apenas numeros inteiros!");
				teclado.nextLine();
				System.out.println("Exeção: " +e.toString());
				System.out.println();
				continue;
			}
			
			
			
		} while(opcao == 1);
		
		System.out.println("*** PROGRAMA ENCERRADO ***");
		teclado.close();
	}
}
```

## 2 – Faça o tratamento de exceções em uma calculadora.
```java
package Exercicio_02; // ÉRIC MARTINS DA SILVA
// 2 – Faça o tratamento de exceções em uma calculadora.
import java.util.InputMismatchException;
import java.util.Scanner;

public class Principal_02 {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        int numero1 = 0, numero2 = 0, resultado = 0;
        int opcao, continuar = 1;

        do {
            try {
                // Solicita os números para o usuário
                System.out.print("Informe o valor do primeiro número: ");
                numero1 = teclado.nextInt();

                System.out.print("Informe o valor do segundo número: ");
                numero2 = teclado.nextInt();

                // Menu
                System.out.println("\n*** MENU ***");
                System.out.println("1 - SOMAR");
                System.out.println("2 - SUBTRAIR");
                System.out.println("3 - MULTIPLICAR");
                System.out.println("4 - DIVIDIR");
                System.out.println("0 - ENCERRAR PROGRAMA");
                System.out.print("\nEscolha uma opção: ");
                opcao = teclado.nextInt();

                switch (opcao) {
                    case 1: // Somar
                        System.out.println("\nVocê escolheu SOMAR");
                        System.out.println("Operação: " + numero1 + " + " + numero2);
                        resultado = numero1 + numero2;
                        break;

                    case 2: // Subtrair
                        System.out.println("\nVocê escolheu SUBTRAIR");
                        System.out.println("Operação: " + numero1 + " - " + numero2);
                        resultado = numero1 - numero2;
                        break;

                    case 3: // Multiplicar
                        System.out.println("\nVocê escolheu MULTIPLICAR");
                        System.out.println("Operação: " + numero1 + " * " + numero2);
                        resultado = numero1 * numero2;
                        break;

                    case 4: // Dividir
                        System.out.println("\nVocê escolheu DIVIDIR");
                        System.out.println("Operação: " + numero1 + " / " + numero2);
                        resultado = numero1 / numero2; // Pode gerar erro se numero2 for 0
                        break;

                    case 0: // Finaliza
                        continuar = 2;
                        break;

                    default:
                        System.out.println("\n*** OPÇÃO INVÁLIDA ***");
                        continue;
                }

                // Mostra o resultado, caso a operação não seja ENCERRAR
                if (opcao != 0) {
                    System.out.println("Resultado: " + resultado);
                }

            } catch (InputMismatchException e) {
                System.out.println("\nExceção capturada: " + e);
                System.out.println("Erro: Entrada inválida! Digite apenas números inteiros\n");
                teclado.nextLine();
                continue;
            } catch (ArithmeticException e) {
                System.out.println("\nExceção capturada: " + e);
                System.out.println("Erro: Operação matemática inválida! " + e.getMessage()+"\n");
                continue;
            } catch (Exception e) {
                System.out.println("\nExceção capturada: " + e);
                System.out.println("Erro inesperado: " + e.getMessage()+"\n");
                continuar = 2;
            }

            if (continuar == 1) {
                System.out.println("\n*** ESCOLHA UMA OPÇÃO ***");
                System.out.println("1 - CONTINUAR | 2 - ENCERRAR");
                System.out.print("Opção: ");
                continuar = teclado.nextInt();
                System.out.println();
            }

        } while (continuar == 1);

        System.out.println("\n*** PROGRAMA ENCERRADO ***");
        teclado.close();
    }
}

```

## 3 – Faça o tratamento de exceções em conversões de valores lidos pelo teclado. Por exemplo, ao ler uma string e converter ela para double.
```java
package Exercicio_03; // ÉRIC MARTINS DA SILVA
// 3 – Faça o tratamento de exceções em conversões de valores lidos pelo teclado. Por exemplo, ao ler uma string e converter ela para double.

import java.util.Scanner;

public class Principal_03 {
	public static void main(String[] args) {
		Scanner teclado = new Scanner(System.in);
		String palavra;
		
		System.out.print("Digite algo para converter para double: ");
		palavra = teclado.nextLine();
		
		try {
			double valor;
			valor = Double.parseDouble(palavra);
			System.out.println("String convertida para double com sucesso! Valor convertido: " + valor);
		}catch(NumberFormatException e){
			System.out.println("Erro! Exceção: " +e.toString());
			System.out.println("Digite algo válido!");
		}
		
		teclado.close();
	}
}
```

## 4 – Pesquise quais são as Exceções existentes que já possuem tratamento e explique brevemente como cada uma funciona. Teste duas exceções.

Em java, uma exceção é "erro" que acontece no meio da execução do programa que acaba encerrando o programa. Existe dois grupos principais de exceções	

### Checked Exceptions (Exceções Verificadas)
* Ocorrem em tempo de compilação e precisam ser tratadas pelo programador usando try-catch ou declaradas com throws.
### Unchecked Exceptions (Exceções Não Verificadas ou RuntimeExceptions)
* Ocorrem em tempo de execução e não são obrigatórias de serem tratadas.

### Principais Exeções e Como Funcionam
* ArithmeticException
	* Tipo: Unchecked (Runtime)
		* Descrição: Ocorre quando há um erro matemático, como divisão por zero.
* ArrayIndexOutOfBoundsException
	* Tipo: Unchecked (Runtime)
		* Descrição: Ocorre quando tentamos acessar uma posição inválida de um array.
* NumberFormatException
	* Tipo: Unchecked (Runtime)
		* Descrição: Lançada quando tentamos converter uma String em um número inválido.
* NullPointerException
	* Tipo: Unchecked (Runtime)
		* Descrição: Ocorre ao tentar acessar um objeto nulo.
* IOException
	* Tipo: Checked
		* Descrição: Relacionada a erros de entrada e saída, como falha ao abrir um arquivo.	
* FileNotFoundException
	* Tipo: Checked
		* Descrição: Ocorre quando um arquivo não é encontrado no caminho especificado.
* ClassNotFoundException
	* Tipo: Checked
 	* Descrição: Lançada quando uma classe não pode ser carregada.

Exemplo 1
```java
package Exercicio_04; // ÉRIC MARTINS DA SILVA

public class Exemplo_01 {

	public static void main(String[] args) {
        try {
            Class.forName("ClasseInexistente"); // Comando para tentar carregar uma classe que não existe
            
        } catch (ClassNotFoundException e) {
            System.out.println("Erro: A classe não foi encontrada!");
            System.out.println("Detalhes da exceção: " + e.getMessage());
        }

        System.out.println("Programa finalizado.");
    }
}
```

Exemplo 2
```java
package Exercicio_04; // ÉRIC MARTINS DA SILVA
import java.io.File;
import java.io.FileReader;
import java.io.IOException;

public class Exemplo_02 {
	public static void main(String[] args) {
        try {
            File arquivo = new File("arquivo_inexistente.txt"); // Comando para tentar abrir um arquivo (que não existe)
            FileReader leitor = new FileReader(arquivo);
        } catch (IOException e) {
            System.out.println("Erro de entrada/saída: Arquivo não encontrado!");
            System.out.println("Detalhes da exceção: " + e.getMessage());
        }

        System.out.println("Programa finalizado.");
    }
}
```
