import java.util.ArrayList;
import java.util.Scanner;

public class BudgetTracker {
    private ArrayList<Double> incomes;
    private ArrayList<Double> expenses;

    public BudgetTracker() {
        incomes = new ArrayList<Double>();
        expenses = new ArrayList<Double>();
    }

    public void addIncome(double amount) {
        incomes.add(amount);
    }

    public void addExpense(double amount) {
        expenses.add(amount);
    }

    public double getTotalIncome() {
        double total = 0;
        for (double amount : incomes) {
            total += amount;
        }
        return total;
    }

    public double getTotalExpense() {
        double total = 0;
        for (double amount : expenses) {
            total += amount;
        }
        return total;
    }

    public double getNetIncome() {
        return getTotalIncome() - getTotalExpense();
    }

    public void printReport() {
        System.out.println("Budget Report:");
        System.out.println("Total Income: " + getTotalIncome());
        System.out.println("Total Expense: " + getTotalExpense());
        System.out.println("Net Income: " + getNetIncome());
    }

    public static void main(String[] args) {
        BudgetTracker tracker = new BudgetTracker();

        while (true) {
            System.out.println("Enter an income or expense (q to quit):");
            String input = scanner.nextLine();
            if (input.equals("q")) {
                break;
            }
            double amount = Double.parseDouble(input.substring(1));
            if (input.charAt(0) == '+') {
                tracker.addIncome(amount);
            } else if (input.charAt(0) == '-') {
                tracker.addExpense(amount);
            }
        }

        tracker.printReport();
    }
}
