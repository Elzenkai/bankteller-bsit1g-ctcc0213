/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package bank_teller;
import java.util.Scanner;

public class Bank_Teller {
private static double balance = 0; 
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("Choices: ");
            System.out.println("1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Your Balance");
            System.out.println("4. Close        ");
            System.out.print("Enter the number of your choice: ");

            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    deposit();
                    break;
                case 2:
                    withdraw();
                    break;
                case 3:
                    checkBalance();
                    break;
                case 4:
                    System.out.println("Bank teller closed.");
                    System.exit(0);
                default:
                    System.out.println("Kindly select a valid choice.");
            }
 
         }
    }

    private static void deposit() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Input the deposit amount: ");
        double amount = scanner.nextDouble();

        if (amount > 0) {
            balance += amount;
            System.out.println("Successful deposit. New balance: $" + balance);
        } else {
            System.out.println("Deposit amount must be a positive value. Please correct your input.");
        }
    }

    private static void withdraw() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Input desired Withdrawal amount: ");
        double amount = scanner.nextDouble();

        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawal successful. New balance: $" + balance);
        } else if (amount > balance) {
            System.out.println("Account balance Insufficient. Please deposit a balance first.");
        } else {
            System.out.println("Withdrawal amount must be a positive value. Please correct your input.");
       }     
   }

    private static void checkBalance() {
        System.out.println("Current balance: $" + balance);
    }   
}

