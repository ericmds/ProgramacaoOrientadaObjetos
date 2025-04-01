# ✦ Exercícios sobre <ins>ENCAPSULAMENTO</ins>

## 1 - Crie uma classe ContaBancaria que possua os atributos saldo e limite. Proteja os atributos utilizando encapsulamento. Crie os métodos get e set para cada atributo. Crie um método saque que permita ao usuário sacar um valor da conta, desde que não ultrapasse o limite da conta. Faça leitura pelo teclado.

### Classe ContaBancaria
```java

```

### Classe Principal
```java

```

## 2 - Crie uma classe Circulo que possua o atributo raio. Proteja o atributo utilizando encapsulamento. Crie os métodos get e set para o atributo. Crie um método calculaArea que calcule a área do círculo e retorne o resultado. Faça leitura pelo teclado dos valores.

### Classe Circulo
```java

```

### Classe Principal
```java

```

## 3 - Crie uma classe Retangulo que possua os atributos base e altura. Proteja os atributos utilizando encapsulamento. Crie os métodos get e set para cada atributo. Crie um método calculaArea que calcule a área do retângulo e retorne o resultado. Faça leitura pelo teclado dos valores.

### Classe Retangulo
```java

```

### Classe principal
```java

```

## 4 - Crie uma classe Carro que possua os atributos marca, modelo e ano. Proteja os atributos utilizando encapsulamento. Crie os métodos get e set para cada atributo. Crie um método exibeDetalhes que exibe os detalhes do carro. Faça leitura pelo teclado dos valores

### Classe Carro
```java
public class Carro {
	private String marca;
	private String modelo;
	private int ano;
	
	public String getMarca() {
		return marca;
	}
	
	public void setMarca(String marca) {
		this.marca = marca;
	}
	
	public String getModelo() {
		return modelo;
	}
	
	public void setModelo(String modelo) {
		this.modelo = modelo;
	}
	
	public int getAno() {
		return ano;
	}
	
	public void setAno(int ano) {
		this.ano = ano;
	}
	
	public void exibeDetalhes() {
		System.out.println("Marca: " + marca);
		System.out.println("Modelo: " + marca);
		System.out.println("Ano: " + marca);
	}
}
```

### Classe Principal
```java

```
