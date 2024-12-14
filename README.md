# T1-MDS
// Projeto: The Hotel - Sistema de Gestão de Hotéis
// Versão: 1.0

// Classe Principal
public class HotelManagementSystem {
    public static void main(String[] args) {
        System.out.println("Bem-vindo ao sistema de gestão de hotéis: The Hotel");
        // Inicializa o sistema
        Hotel hotel = new Hotel("Hotel Exemplo");
        hotel.run();
    }
}

// Classe para representar o hotel
class Hotel {
    private String nome;

    public Hotel(String nome) {
        this.nome = nome;
    }

    public void run() {
        // Menu inicial (exemplo simplificado)
        System.out.println("Sistema iniciado para: " + nome);
        System.out.println("1. Gerir Quartos");
        System.out.println("2. Gerir Reservas");
        System.out.println("3. Gerir Manutenção");
        System.out.println("4. Sair");
        // TODO: Implementar interações do usuário
    }
}

// Classe para representar quartos
class Quarto {
    private int numero;
    private int capacidadeMaxima;
    private int numeroCamas;
    private String tipoVista;
    private boolean cozinha;
    private int numeroBanheiros;
    private boolean varanda;

    public Quarto(int numero, int capacidadeMaxima, int numeroCamas, String tipoVista, boolean cozinha, int numeroBanheiros, boolean varanda) {
        this.numero = numero;
        this.capacidadeMaxima = capacidadeMaxima;
        this.numeroCamas = numeroCamas;
        this.tipoVista = tipoVista;
        this.cozinha = cozinha;
        this.numeroBanheiros = numeroBanheiros;
        this.varanda = varanda;
    }

    public void editarQuarto(int capacidadeMaxima, int numeroCamas, String tipoVista, boolean cozinha, int numeroBanheiros, boolean varanda) {
        this.capacidadeMaxima = capacidadeMaxima;
        this.numeroCamas = numeroCamas;
        this.tipoVista = tipoVista;
        this.cozinha = cozinha;
        this.numeroBanheiros = numeroBanheiros;
        this.varanda = varanda;
        System.out.println("Quarto " + numero + " atualizado com sucesso.");
    }

    public void exibirInformacoes() {
        System.out.println("Quarto " + numero);
        System.out.println("Capacidade: " + capacidadeMaxima + " hóspedes");
        System.out.println("Camas: " + numeroCamas);
        System.out.println("Vista: " + tipoVista);
        System.out.println("Cozinha: " + (cozinha ? "Sim" : "Não"));
        System.out.println("Banheiros: " + numeroBanheiros);
        System.out.println("Varanda: " + (varanda ? "Sim" : "Não"));
    }
}

// Classe para representar reservas
class Reserva {
    private int id;
    private String hospede;
    private String dataEntrada;
    private String dataSaida;
    private Quarto quarto;

    public Reserva(int id, String hospede, String dataEntrada, String dataSaida, Quarto quarto) {
        this.id = id;
        this.hospede = hospede;
        this.dataEntrada = dataEntrada;
        this.dataSaida = dataSaida;
        this.quarto = quarto;
    }

    public void exibirDetalhes() {
        System.out.println("Reserva " + id);
        System.out.println("Hóspede: " + hospede);
        System.out.println("Entrada: " + dataEntrada);
        System.out.println("Saída: " + dataSaida);
        System.out.println("Quarto: " + quarto);
    }
}

// Classe para representar manutenção
class Manutencao {
    private int id;
    private Quarto quarto;
    private String tipo;
    private String data;
    private String status;

    public Manutencao(int id, Quarto quarto, String tipo, String data, String status) {
        this.id = id;
        this.quarto = quarto;
        this.tipo = tipo;
        this.data = data;
        this.status = status;
    }

    public void exibirDetalhes() {
        System.out.println("Manutenção " + id);
        System.out.println("Quarto: " + quarto);
        System.out.println("Tipo: " + tipo);
        System.out.println("Data: " + data);
        System.out.println("Status: " + status);
    }

    public void atualizarStatus(String novoStatus) {
        this.status = novoStatus;
        System.out.println("Status atualizado para: " + status);
    }
}
