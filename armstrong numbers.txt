import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N1 = scanner.nextInt();
        int N2 = scanner.nextInt();

        printArmstrongNumbers(N1, N2);

        scanner.close();
    }

    public static void printArmstrongNumbers(int N1, int N2) {
        for (int num = N1; num <= N2; num++) {
            if (isArmstrongNumber(num)) {
                System.out.println(num);
            }
        }
    }

    public static boolean isArmstrongNumber(int num) {
        int originalNum = num;
        int sum = 0;
        int numOfDigits = (int) Math.log10(num) + 1;

        while (num > 0) {
            int digit = num % 10;
            sum += Math.pow(digit, numOfDigits);
            num /= 10;
        }

        return sum == originalNum;
    }
}
