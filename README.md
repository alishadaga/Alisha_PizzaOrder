/*
 * COPYRIGHT. HSBC HOLDINGS PLC 2015. ALL RIGHTS RESERVED.
 * 
 * This software is only to be used for the purpose for which it has been
 * provided. No part of it is to be reproduced, disassembled, transmitted,
 * stored in a retrieval system nor translated in any human or computer
 * language in any way or for any other purposes whatsoever without the prior
 * written consent of HSBC Holdings plc.
 */

/**
 * <p>
 * <b> TODO : Insert description of the class's responsibility/role. </b>
 * </p>
 */

/**
 * This program allows the user to order a pizza
 */
import java.text.DecimalFormat;
import java.util.Scanner;

public class PizzaOrder {
    public static void main(final String[] args) {
        // TASK #5 Create a DecimalFormat object with 2 decimal places

        // Create a Scanner object to read input
        Scanner keyboard = new Scanner(System.in);
        DecimalFormat df = new DecimalFormat("#.##");

        String firstName; // user's first name
        boolean discount = false; // flag, true if user is eligible for
                                  // discount
        String inches; // size of the pizza
        char crustType; // code for type of crust
        String crust = "Hand-tossed"; // name of crust
        double cost = 0.0; // cost of the pizza
        final double TAX_RATE = .08; // sales tax rate
        double tax; // amount of tax
        char choice; // user's choice
        String input; // user input
        String toppings = "Cheese "; // list of toppings
        int numberOfToppings = 0; // number of toppings

        // prompt user and get first name
        System.out.println("Welcome to Dominos Pizza");
        System.out.print("Enter your first name:  ");
        firstName = keyboard.nextLine();

        // determine if user is eligible for discount by
        // having the same first name as one of the owners
        // ADD LINES HERE FOR TASK #1

        // prompt user and get pizza size choice
        System.out.println("Pizza Size        Cost");
        System.out.println("        S          400");
        System.out.println("        M          600");
        System.out.println("        L          800");
        System.out.println("What size pizza would you like?");
        System.out.print("S,M and L (enter the letter only): ");
        inches = keyboard.nextLine();
        if (inches.equals("S")) {
            cost = 400;
        } else if (inches.equals("M")) {
            cost = 600;
        } else if (inches.equals("L")) {
            cost = 800;
        } else if (!inches.equals("S") && !inches.equals("M") && !inches.equals("L")) {
            System.out.println("The Size you have entered is illegal, your pizza size will    be set to M inches. ");
            cost = 600;
        }

        // set price and size of pizza ordered
        // ADD LINES HERE FOR TASK #2


        // prompt user and get crust choice
        System.out.println("What type of crust do you want? ");
        System.out.print("Thin-crust, or " + " Thick-Crust (enter Tk or Tn ): ");
        input = keyboard.nextLine();
        crustType = input.charAt(0);

        // set user's crust choice on pizza ordered
        // ADD LINES FOR TASK #3

        // prompt user and get topping choices one at a time
        System.out.println("All pizzas come with cheese.");
        System.out.println("Additional toppings are 40 Rs each," + " choose from");
        System.out.println("Pepperoni, Sausage, Onion, Mushroom");

        // if topping is desired,
        // add to topping list and number of toppings
        System.out.print("Do you want Pepperoni?  (Y/N):  ");
        input = keyboard.nextLine();
        choice = input.charAt(0);
        if (choice == 'Y' || choice == 'y') {
            numberOfToppings += 1;
            toppings = toppings + "Pepperoni ";
        }
        System.out.print("Do you want Sausage?  (Y/N):  ");
        input = keyboard.nextLine();
        choice = input.charAt(0);
        if (choice == 'Y' || choice == 'y') {
            numberOfToppings += 1;
            toppings = toppings + "Sausage ";
        }
        System.out.print("Do you want Onion?  (Y/N):  ");
        input = keyboard.nextLine();
        choice = input.charAt(0);
        if (choice == 'Y' || choice == 'y') {
            numberOfToppings += 1;
            toppings = toppings + "Onion ";
        }
        System.out.print("Do you want Mushroom?  (Y/N):  ");
        input = keyboard.nextLine();
        choice = input.charAt(0);
        if (choice == 'Y' || choice == 'y') {
            numberOfToppings += 1;
            toppings = toppings + "Mushroom ";
        }

        // add additional toppings cost to cost of pizza
        cost = cost + (40 * numberOfToppings);

        // display order confirmation
        System.out.println();
        System.out.println("Your order is as follows: ");
        System.out.println(inches + " inch pizza");
        System.out.println(crust + " crust");
        System.out.println(toppings);

        // apply discount if user is elibible
        // ADD LINES FOR TASK #4 HERE

        // EDIT PROGRAM FOR TASK #5
        // SO ALL MONEY OUTPUT APPEARS WITH 2 DECIMAL PLACES
        System.out.println("The cost of your order is: " + df.format(cost));

        // calculate and display tax and total cost
        tax = cost * TAX_RATE;
        System.out.println("The tax is: " + df.format(tax));
        System.out.println("The total due is: " + df.format(tax + cost));

        System.out.println("Your order will be ready for pickup in 30 minutes.");
    }
}
