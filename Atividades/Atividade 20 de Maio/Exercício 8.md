# 8) Crie uma interface chamada AcessoDados que contenha os seguintes métodos: conectar(), desconectar(), inserir(), atualizar() e excluir(). Crie uma classe BancoDeDados que implemente a interface AcessoDados. Implemente os métodos da interface para que eles realizem as operações de conectar-se ao banco de dados, desconectar-se, inserir dados, atualizar dados e excluir dados.

## AcessoDados
```java
package Exercicio08;

public interface AcessoDados {
	void conectar();

	void desconectar();

	void inserir();

	void atualizar();

	void excluir();
}
```
## BancoDeDados
```java
package Exercicio08;

public class BancoDeDados implements AcessoDados {

    private boolean conectado = false;

    @Override
    public void conectar() {
        if (!conectado) {
            conectado = true;
            System.out.println("Conectado ao banco de dados.");
        } else {
            System.out.println("Já está conectado.");
        }
    }

    @Override
    public void desconectar() {
        if (conectado) {
            conectado = false;
            System.out.println("Desconectado do banco de dados.");
        } else {
            System.out.println("Não está conectado.");
        }
    }

    @Override
    public void inserir() {
        if (conectado) {
            System.out.println("Inserindo dados no banco de dados...");
        } else {
            System.out.println("Erro: não está conectado ao banco.");
        }
    }

    @Override
    public void atualizar() {
        if (conectado) {
            System.out.println("Atualizando dados no banco de dados...");
        } else {
            System.out.println("Erro: não está conectado ao banco.");
        }
    }

    @Override
    public void excluir() {
        if (conectado) {
            System.out.println("Excluindo dados do banco de dados...");
        } else {
            System.out.println("Erro: não está conectado ao banco.");
        }
    }
}

```
## Principal
```java
package Exercicio08;

public class Principal {
    public static void main(String[] args) {
        BancoDeDados banco = new BancoDeDados();

        banco.conectar();
        banco.inserir();
        banco.atualizar();
        banco.excluir();
        banco.desconectar();
    }
}

```
