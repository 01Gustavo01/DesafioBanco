import java.util.*;

public class Main {
    public static double adicionarDinheiro(double saldo, double valorAdicionado) {
            return saldo + valorAdicionado;
        }
    public static double tirarDinheiro(double saldo, double valorTransferido) {
        if (saldo - valorTransferido < 0) {
            System.out.println("Não é possível tirar esse valor da conta atual.");
            return saldo;
        }
        return saldo - valorTransferido;
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String nomeCliente = "Gustavo";
        String tipoConta = "Corrente";
        double saldoCliente = 500;
        boolean continuar = true;

        System.out.println("***************************************");
        System.out.println("Dados iniciais do Cliente:              ");
        System.out.println("Nome:              " + nomeCliente);
        System.out.println("Tipo Conta:        " + tipoConta);
        System.out.println("Saldo Inicial:     R$" + saldoCliente);
        System.out.println("***************************************/n");

        while (continuar){

            System.out.println("Operações\n");
            System.out.println("1- Consultar saldos");
            System.out.println("2- Receber valor");
            System.out.println("3- Transferir valor");
            System.out.println("4- Sair\n\n");
            System.out.println("Digite a opção desejada: ");

            int opcao = scanner.nextInt();

            switch (opcao){
                case 1:
                    System.out.println("\n\nSeu saldo é de: R$" + saldoCliente + "\n\n");
                    break;
                case 2:
                    System.out.println("\nDigite valor a ser depositado: R$\n");
                    double adicionarDinheiro = scanner.nextDouble();
                    saldoCliente = adicionarDinheiro(saldoCliente, adicionarDinheiro);
                    System.out.println("Seu saldo é de: R$" + saldoCliente);
                    break;
                case 3:
                    System.out.println("\nDigite valor a ser transferido: R$\n");
                    double tirarDinheiro = scanner.nextDouble();
                    saldoCliente = tirarDinheiro(saldoCliente, tirarDinheiro);
                    System.out.println("Seu saldo é de: R$" + saldoCliente);
                    break;
                case 4:
                    continuar = false;
                    break;
                default:
                    System.out.println("\nOpção Inválida!\n");
                    break;
            }

        }
        System.out.println("Programa encerrado.");
        scanner.close();

    }
}
