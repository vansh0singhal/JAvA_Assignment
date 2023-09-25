import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        
        for (int i = 0; i < N; i++) {
            long carNumber = scanner.nextLong();
            
            String result = checkOddEvenRule(carNumber);
            
            System.out.println(result);
        }
        
        scanner.close();
    }

    public static String checkOddEvenRule(long carNumber) {
        int sumEven = 0;
        int sumOdd = 0;
        
        while (carNumber > 0) {
            int digit = (int) (carNumber % 10);
            if (digit % 2 == 0) {
                sumEven += digit;
            } else {
                sumOdd += digit;
            }
            carNumber /= 10;
        }
        
        if (sumEven % 4 == 0 || sumOdd % 3 == 0) {
            return "Yes";
        } else {
            return "No";
        }
    }
}
