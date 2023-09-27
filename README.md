import java.util.Scanner;

public class Tax {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        char continueCalculations;

        do {
            System.out.print("Enter your weekly income: $");
            double weeklyIncome = input.nextDouble();

            double taxRate;
            double taxWithholding;

            if (weeklyIncome < 500) {
                taxRate = 0.10;
            } else if (weeklyIncome < 1500) {
                taxRate = 0.15;
            } else if (weeklyIncome < 2500) {
                taxRate = 0.20;
            } else {
                taxRate = 0.30;
            }

            taxWithholding = weeklyIncome * taxRate;
            System.out.printf("Your weekly tax withholding: $%.2f%n", taxWithholding);

            System.out.print("Do you want to calculate again? (y/n): ");
            continueCalculations = input.next().charAt(0);
        } while (continueCalculations == 'y' || continueCalculations == 'Y');

        input.close();
    }
}
