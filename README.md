import java.util.Scanner;

public class SimpleCalculator {

    // Method to perform addition
    public static double add(double a, double b) {
        return a + b;
    }

    // Method to perform subtraction
    public static double subtract(double a, double b) {
        return a - b;
    }

    // Method to perform multiplication
    public static double multiply(double a, double b) {
        return a * b;
    }

    // Method to perform division
    public static double divide(double a, double b) {
        if (b == 0) {
            System.out.println("Error: Division by zero is not allowed.");
            return Double.NaN; // Return NaN (Not a Number) if division by zero
        }
        return a / b;
    }

    public static void main(String[] args) {
        // Create Scanner object to take input from the user
        Scanner scanner = new Scanner(System.in);

        System.out.println("Simple Calculator");
        System.out.println("-------------------");
        
        // Input: First number
        System.out.print("Enter the first number: ");
        double num1 = scanner.nextDouble();

        // Input: Second number
        System.out.print("Enter the second number: ");
        double num2 = scanner.nextDouble();

        // Input: Choice of operation
        System.out.println("Choose an operation:");
        System.out.println("1. Addition");
        System.out.println("2. Subtraction");
        System.out.println("3. Multiplication");
        System.out.println("4. Division");

        System.out.print("Enter your choice (1/2/3/4): ");
        int choice = scanner.nextInt();

        // Perform the operation based on the user's choice
        double result = 0;
        switch (choice) {
            case 1:
                result = add(num1, num2);
                System.out.println("Result of Addition: " + result);
                break;
            case 2:
                result = subtract(num1, num2);
                System.out.println("Result of Subtraction: " + result);
                break;
            case 3:
                result = multiply(num1, num2);
                System.out.println("Result of Multiplication: " + result);
                break;
            case 4:
                result = divide(num1, num2);
                if (!Double.isNaN(result)) {
                    System.out.println("Result of Division: " + result);
                }
                break;
            default:
                System.out.println("Invalid choice! Please choose a valid operation.");
        }

        // Close the scanner to prevent resource leak
        scanner.close();
    }
}
