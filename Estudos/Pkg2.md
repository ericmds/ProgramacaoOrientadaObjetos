# Controlador
```java
package Pkg2;

public interface Controlador {
	public abstract void ligar();
	public abstract void desligar();
	public abstract void abrirMenu();
	public abstract void fecharMenu();
	public abstract void maisVolume();
	public abstract void menosVolume();
	public abstract void ligarMudo();
	public abstract void desligarMudo();
	public abstract void play();
	public abstract void pause();
}

```
# ControleRemoto
```java
package Pkg2;

public class ControleRemoto implements Controlador {
	private int volume;
	private boolean ligado;
	private boolean tocando;

	public ControleRemoto() {
		this.volume = 50;
		this.ligado = false;
		this.tocando = false;
	}

	private int getVolume() {
		return volume;
	}

	private void setVolume(int volume) {
		this.volume = volume;
	}

	private boolean getLigado() {
		return ligado;
	}

	private void setLigado(boolean ligado) {
		this.ligado = ligado;
	}

	private boolean getTocando() {
		return tocando;
	}

	private void setTocando(boolean tocando) {
		this.tocando = tocando;
	}

	@Override
	public void ligar() {
		this.setLigado(true);

	}

	@Override
	public void desligar() {
		this.setLigado(false);

	}

	@Override
	public void abrirMenu() {
		System.out.println("----- MENU -----");
		System.out.println("Está ligado? " + this.getLigado());
		System.out.println("Está tocando? " + this.getTocando());
		System.out.print("Volume: " + this.getVolume() + " ");
		for (int i = 0; i <= this.getVolume(); i += 10) {
			System.out.print("|");
		}

	}

	@Override
	public void fecharMenu() {
		System.out.println("\nFechando menu...");
	}

	@Override
	public void maisVolume() {
		if (this.getLigado()) {
			this.setVolume(this.getVolume() + 5);
		}
	}

	@Override
	public void menosVolume() {
		if (this.getLigado()) {
			this.setVolume(this.getVolume() - 5);
		}
	}

	@Override
	public void ligarMudo() {
		if (this.getLigado() && this.getVolume() > 0) {
			this.setVolume(0);
		}
	}

	@Override
	public void desligarMudo() {
		if (this.getLigado() && this.getVolume() == 0) {
			this.setVolume(50);
		}
	}

	@Override
	public void play() {
		if (this.getLigado() && !(this.getTocando())) {
			this.setTocando(true);
		}
	}

	@Override
	public void pause() {
		if (this.getLigado() && this.getTocando()) {
			this.setTocando(false);
		}
	}

}

```
# Principal
```java
package Pkg2;

public class Principal {

	public static void main(String[] args) {
		ControleRemoto c = new ControleRemoto();
		c.ligar();
		c.maisVolume();
		c.play();
		c.abrirMenu();
		c.fecharMenu();

	}

}

```
