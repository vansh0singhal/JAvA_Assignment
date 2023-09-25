import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        long N = scanner.nextLong();

        // Initialize variables to store the sums of odd and even placed digits
        long oddSum = 0;
        long evenSum = 0;

        // Variable to keep track of the position of the digit
        int position = 1;

        // Loop through each digit of N
        while (N > 0) {
            long digit = N % 10; // Get the last digit
            if (position % 2 == 1) {
                // Odd placed digit
                oddSum += digit;
            } else {
                // Even placed digit
                evenSum += digit;
            }
            N /= 10; // Remove the last digit
            position++;
        }

        // Print the sums
        System.out.println(oddSum);
        System.out.println(evenSum);

        scanner.close();
    }
}
