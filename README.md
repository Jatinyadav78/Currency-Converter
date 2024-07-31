import java.util.Scanner;

public class CurrencyConverter {
    // Define exchange rates
    private static final double USD_TO_EUR = 0.85;  // Example rate
    private static final double USD_TO_GBP = 0.75;  // Example rate
    private static final double EUR_TO_USD = 1 / USD_TO_EUR;
    private static final double GBP_TO_USD = 1 / USD_TO_GBP;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Currency Converter");
        System.out.println("1. USD to EUR");
        System.out.println("2. USD to GBP");
        System.out.println("3. EUR to USD");
        System.out.println("4. GBP to USD");
        System.out.print("Choose an option (1-4): ");
        int option = scanner.nextInt();

        System.out.print("Enter the amount to convert: ");
        double amount = scanner.nextDouble();

        double convertedAmount = 0;

        switch (option) {
            case 1:
                convertedAmount = convertUSDtoEUR(amount);
                System.out.printf("USD %.2f = EUR %.2f%n", amount, convertedAmount);
                break;
            case 2:
                convertedAmount = convertUSDtoGBP(amount);
                System.out.printf("USD %.2f = GBP %.2f%n", amount, convertedAmount);
                break;
            case 3:
                convertedAmount = convertEURtoUSD(amount);
                System.out.printf("EUR %.2f = USD %.2f%n", amount, convertedAmount);
                break;
            case 4:
                convertedAmount = convertGBPtoUSD(amount);
                System.out.printf("GBP %.2f = USD %.2f%n", amount, convertedAmount);
                break;
            default:
                System.out.println("Invalid option.");
                break;
        }

        scanner.close();
    }

    // Conversion methods
    public static double convertUSDtoEUR(double amount) {
        return amount * USD_TO_EUR;
    }

    public static double convertUSDtoGBP(double amount) {
        return amount * USD_TO_GBP;
    }

    public static double convertEURtoUSD(double amount) {
        return amount * EUR_TO_USD;
    }

    public static double convertGBPtoUSD(double amount) {
        return amount * GBP_TO_USD;
    }
}

