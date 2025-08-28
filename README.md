# OOPS---EXP4
QUESTION - FRUIT PURCHASE MENU

CODE:
package oops2;
import java.util.Scanner;
class Fruit {
    private String name;
    private double pricePerKg;
    private double quantity;
    public Fruit(String name, double pricePerKg, double quantity) {
        this.name = name;
        this.pricePerKg = pricePerKg;
        this.quantity = quantity;
    }
    public double calculateTotalCost() {
        return pricePerKg * quantity;
    }
    public void displayDetails() {
        System.out.println("\nFruit Name: " + name);
        System.out.println("Price per Kg: ₹" + pricePerKg);
        System.out.println("Quantity: " + quantity + " kg");
        System.out.println("Total Cost: ₹" + calculateTotalCost());
    }
    public void updatePrice(double newPrice) {
        pricePerKg = newPrice;
        System.out.println("Price updated successfully!");
    }
    public void updateQuantity(double newQuantity) {
        quantity = newQuantity;
        System.out.println("Quantity updated successfully!");
    }
}
public class FruitPurchaseMenu {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("URK24CS6006 PUITHA");
        System.out.print("Enter Fruit Name: ");
        String name1 = sc.nextLine();
        System.out.print("Enter Price per Kg: ");
        double price1 = sc.nextDouble();
        System.out.print("Enter Quantity (in Kg): ");
        double qty1 = sc.nextDouble();
        sc.nextLine(); 
        Fruit fruit = new Fruit(name1, price1, qty1);
        int choice;
        do {
            System.out.println("\n----- Fruit Menu -----");
            System.out.println("1. Display Fruit Details");
            System.out.println("2. Update Price");
            System.out.println("3. Update Quantity");
            System.out.println("4. Calculate Total Cost");
            System.out.println("5. Exit");
            System.out.print("Enter your choice: ");
            choice = sc.nextInt();
            switch (choice) {
                case 1:
                    fruit.displayDetails();
                    break;
                case 2:
                    System.out.print("Enter New Price: ");
                    double newPrice = sc.nextDouble();
                    fruit.updatePrice(newPrice);
                    break;
                case 3:
                    System.out.print("Enter New Quantity (Kg): ");
                    double newQty = sc.nextDouble();
                    fruit.updateQuantity(newQty);
                    break;
                case 4:
                    System.out.println("Total Cost: ₹" + fruit.calculateTotalCost());
                    break;
                case 5:
                    System.out.println("Exiting... Thank you!");
                    break;
                default:
                    System.out.println("Invalid choice! Try again.");
            }

        } while (choice != 5);
    }
}


