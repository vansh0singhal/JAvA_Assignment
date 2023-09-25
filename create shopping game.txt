import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int T = scanner.nextInt();

        for (int t = 0; t < T; t++) {
            int M = scanner.nextInt();
            int N = scanner.nextInt();

            String winner = determineWinner(M, N);

            System.out.println(winner);
        }

        scanner.close();
    }

    public static String determineWinner(int M, int N) {
        int aayush = 1;
        int harshit = 2;

        while (true) {
            if (aayush <= M) {
                M -= aayush;
                aayush += 2;
            } else {
                return "Harshit";
            }

            if (harshit <= N) {
                N -= harshit;
                harshit += 2;
            } else {
                return "Aayush";
            }
        }
    }
}
