# TestBankAccount
13b. import java.util.Scanner;

public class TestBankAccount {
    public static void main(String[] args) {
        // Create four BankAccount objects
        BankAccount account1 = new BankAccount();
        BankAccount account2 = new BankAccount();
        BankAccount account3 = getData(); // Prompt user for data
        BankAccount account4 = new BankAccount(); // Default values

        // Display and process account data
        showValues(account1);
        showValues(account2);
        showValues(account3);
        showValues(account4);
    }

    // Method to prompt user for BankAccount data
    public static BankAccount getData() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter account number: ");
        int accountNumber = scanner.nextInt();
        System.out.print("Enter owner's name: ");
        scanner.nextLine(); // Consume newline
        String ownerName = scanner.nextLine();
        System.out.print("Enter account balance: $");
        double accountBalance = scanner.nextDouble();
        scanner.close();

        BankAccount account = new BankAccount();
        account.setAccountNumber(accountNumber);
        account.setOwnerName(ownerName);
        account.setAccountBalance(accountBalance);

        return account;
    }

    // Method to display account data, deduct monthly fee, and explain policy
    public static void showValues(BankAccount account) {
        System.out.println("\nAccount Number: " + account.getAccountNumber());
        System.out.println("Owner's Name: " + account.getOwnerName());
        System.out.println("Account Balance: $" + account.getAccountBalance());

        account.deductMonthlyFee();
        System.out.println("Deducted Monthly Fee: $4.00");
        System.out.println("Updated Balance: $" + account.getAccountBalance());

        BankAccount.explainAccountPolicy();
    }
}
