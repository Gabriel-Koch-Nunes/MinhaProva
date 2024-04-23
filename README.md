import javax.swing.*;
import java.util.ArrayList;
import java.util.Scanner;

class Jogador {
    String nome;
    int votos;

    public Jogador(String nome) {
        this.nome = nome;
        this.votos = 0;
    }

    public void incrementaUmVoto() {
        this.votos++;
    }

    public String getNome() {
        return nome;
    }

    public int getVotos() {
        return votos;
    }
}

public class CasaMaisVigiada {

    public static void main(String[] args) {
        ArrayList<Jogador> jogadores = new ArrayList<>();

        jogadores.add(new Jogador("Alane Dias"));
        jogadores.add(new Jogador("Beatriz Reis"));
        jogadores.add(new Jogador("Davi Brito"));
        jogadores.add(new Jogador("Deniziane Ferreira"));
        jogadores.add(new Jogador("Fernanda Bande"));
        jogadores.add(new Jogador("Giovanna Lima"));
        jogadores.add(new Jogador("Giovannna Pitel"));
        jogadores.add(new Jogador("Isabelle Nogueira"));
        jogadores.add(new Jogador("Juninho"));
        jogadores.add(new Jogador("Leidy Elin"));
        jogadores.add(new Jogador("Lucas Henrique"));
        jogadores.add(new Jogador("Lucas Luigi"));
        jogadores.add(new Jogador("Lucas Pizane"));
        jogadores.add(new Jogador("Marcus Vinicius"));
        jogadores.add(new Jogador("Matteus Amaral"));
        jogadores.add(new Jogador("Maycon Cosmer"));
        jogadores.add(new Jogador("MC Bin Laden"));
        jogadores.add(new Jogador("Michel Nogueira"));
        jogadores.add(new Jogador("Nizam"));
        jogadores.add(new Jogador("Raquele Cardozo"));
        jogadores.add(new Jogador("Rodriguinho"));
        jogadores.add(new Jogador("Thalyta Alves"));
        jogadores.add(new Jogador("Vanessa Lopes"));
        jogadores.add(new Jogador("Vinicius Rodrigues"));
        jogadores.add(new Jogador("Wanessa Camargo"));
        jogadores.add(new Jogador("Yasmin Brunet"));

        Scanner scn = new Scanner(System.in);
        String voto;
        int maxVotos = 0;
        Jogador eliminado = null;


        while (true) {
            // Apresentar menu de opções
            System.out.println("**********************");
            System.out.println("\n\nVotação BBB");
            System.out.println("1. Em Quem você Vota");
            System.out.println("2. Exibir participante com mais votos");
            System.out.println("3. Sair");
            System.out.println("**********************");
            System.out.print("Digite sua opção: ");

            int opcao = scn.nextInt();
            scn.nextLine();


            System.out.println("Quem você vota para sair da casa?");
            voto = scn.nextLine();
            if (voto.equalsIgnoreCase("sair")) {
                break;
            }
            boolean encontrado = false;
            for (Jogador jogador : jogadores) {
                if (jogador.getNome().equalsIgnoreCase(voto)) {
                    jogador.incrementaUmVoto();
                    if (jogador.getVotos() > maxVotos) {
                        maxVotos = jogador.getVotos();
                        eliminado = jogador;
                    }
                    encontrado = true;
                }
            }
            if (!encontrado) {
                System.out.println("Jogador não encontrado.");
            }
        }


        System.out.println("Se eu conseguir mover montanhas, se eu conseguir surfar um tsunami, "
                + "se eu conseguir domar o sol, se eu conseguir fazer o mar virar sertão, "
                + "se eu conseguir dizer o que eu nunca vou conseguir dizer, aí terá chegado o dia "
                + "em que eu vou conseguir te eliminar com alegria. Com " + maxVotos + " votos, é "
                + "você quem sai " + eliminado.getNome());


    }
}
