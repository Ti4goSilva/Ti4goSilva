/******************************************************************************

Atividade, criar código em Java, um sistema simples de cadastro
e exibição de informações que usa interface, classes abstratas,
herança e polimorfismo para organizar dados de clientes,
funcionários e produtos (eletrônicos, móveis, decoração, vestuário, vídeo games,
brinquedos e utilitários) e funcionários responsáveis pelas áreas. 

Esse
programa simula varejistas como CASAS BAHIA DESENVOLVEDOR(TIAGO) TESTER(JUNIO)
testar o codigo com o @Test JUnit em Java OO.

*******************************************************************************/
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

// Interface de Cadastro
interface Cadastro {
    void cadastrar();
}

// Interface de Exibição
interface Exibicao {
    void exibir();
}

// Classe Abstrata Pessoa
abstract class Pessoa {
    protected String nome;
    protected String cpf;

    public Pessoa(String nome, String cpf) {
        this.nome = nome;
        this.cpf = cpf;
    }

    public abstract void exibir();
}

// Classe Cliente
class Cliente extends Pessoa implements Exibicao {
    public Cliente(String nome, String cpf) {
        super(nome, cpf);
    }

    @Override
    public void exibir() {
        System.out.println("Cliente: " + nome + ", CPF: " + cpf);
    }
}

// Classe Funcionario
class Funcionario extends Pessoa implements Exibicao {
    private String setor;

    public Funcionario(String nome, String cpf, String setor) {
        super(nome, cpf);
        this.setor = setor;
    }

    @Override
    public void exibir() {
        System.out.println("Funcionário: " + nome + ", CPF: " + cpf + ", Setor: " + setor);
    }
}

// Classe Abstrata Produto
abstract class Produto {
    protected String nome;
    protected double preco;

    public Produto(String nome, double preco) {
        this.nome = nome;
        this.preco = preco;
    }

    public abstract void exibir();
}

// Classes de Produtos
class Eletronico extends Produto implements Exibicao {
    public Eletronico(String nome, double preco) {
        super(nome, preco);
    }

    @Override
    public void exibir() {
        System.out.println("Produto Eletrônico: " + nome + ", Preço: R$" + preco);
    }
}

class Movel extends Produto implements Exibicao {
    public Movel(String nome, double preco) {
        super(nome, preco);
    }

    @Override
    public void exibir() {
        System.out.println("Móvel: " + nome + ", Preço: R$" + preco);
    }
}

class Decoracao extends Produto implements Exibicao {
    public Decoracao(String nome, double preco) {
        super(nome, preco);
    }

    @Override
    public void exibir() {
        System.out.println("Decoração: " + nome + ", Preço: R$" + preco);
    }
}

// Mais classes de produtos (Vestuario, VideoGame, Brinquedo, Utilitario)
class Vestuario extends Produto implements Exibicao {
    public Vestuario(String nome, double preco) {
        super(nome, preco);
    }

    @Override
    public void exibir() {
        System.out.println("Vestuário: " + nome + ", Preço: R$" + preco);
    }
}

class VideoGame extends Produto implements Exibicao {
    public VideoGame(String nome, double preco) {
        super(nome, preco);
    }

    @Override
    public void exibir() {
        System.out.println("Video Game: " + nome + ", Preço: R$" + preco);
    }
}

class Brinquedo extends Produto implements Exibicao {
    public Brinquedo(String nome, double preco) {
        super(nome, preco);
    }

    @Override
    public void exibir() {
        System.out.println("Brinquedo: " + nome + ", Preço: R$" + preco);
    }
}

class Utilitario extends Produto implements Exibicao {
    public Utilitario(String nome, double preco) {
        super(nome, preco);
    }

    @Override
    public void exibir() {
        System.out.println("Utilitário: " + nome + ", Preço: R$" + preco);
    }
}

// Classe Principal
public class Main {
    public static void main(String[] args) {
        Cliente cliente1 = new Cliente("João da Silva", "123.456.789-00");
        Funcionario funcionario1 = new Funcionario("Maria Oliveira", "987.654.321-00", "Eletrônicos");

        Produto eletronico1 = new Eletronico("Televisor", 1500.00);
        Produto movel1 = new Movel("Sofá", 800.00);
        Produto decoracao1 = new Decoracao("Quadro", 150.00);
        Produto vestuario1 = new Vestuario("Camiseta", 50.00);
        Produto videoGame1 = new VideoGame("PlayStation 5", 3000.00);
        Produto brinquedo1 = new Brinquedo("Carrinho", 100.00);
        Produto utilitario1 = new Utilitario("Faca de cozinha", 30.00);

        // Exibindo informações
        cliente1.exibir();
        funcionario1.exibir();

        eletronico1.exibir();
        movel1.exibir();
        decoracao1.exibir();
        vestuario1.exibir();
        videoGame1.exibir();
        brinquedo1.exibir();
        utilitario1.exibir();
    }
}
