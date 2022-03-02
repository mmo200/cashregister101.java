# cashregister101.java
it is a cash register please let me know how i can improve to be more efficient its in java main (2022-03-02)

/*
michael nolk 
Feb 27 2022
ICS 4U1
*/

//import java scanner 
import java.util.Scanner;
public class MyProgram
{
    public static void main(String[] args)
    {
      //create varible for my bils 
      double fiveBill = 5.00;
      double tenBill = 10.00;
      double twentyBill = 20.00;
      double fifthyBill = 50.00;
      double hundredBill = 100.00; 
      //create the varible for the coins 
      double quarter = 0.25;
      double dime = 0.10;
      double nickel = 0.05;
       
        //create new scanner object 
        Scanner s = new Scanner(System.in); 
        
        // prompt the cashier for the cost of the item  
        System.out.println("enter price of the item: ");
        double cost = s.nextDouble();
       
         //include tax and output it 
        double amountAfterTax = tax(cost);
        System.out.println("amount after tax = " + amountAfterTax);
       
        //prompt the cashier for the amount of change given
         System.out.println("enter cash given: ");
        double cash = s.nextDouble(); 
        
        // create varible for my key words   
        String coinMethod = "Coin";
        String cashMethod = "Cash";
    
        
    
        // create a loop and allow the program to execute over and over again 
       
        
        
        while(true){
      // create if statement to make sure the cash given, is enough 
         if(amountAfterTax > cash){
            System.out.println("          !Err0r!        ");
            System.out.println("*******  N0t En0ugh  *******");
            break;
         }
       
        
        
       
        System.out.println(" ");
        System.out.print(" for the coin method type 'Coin' or type 'Cash' cash method ");
        s.nextLine();
        String input1 = s.nextLine();
       
        // create varibles for my change and invoe my method 
        double changeBack = change(cash, cost);
        
        //output the change owed and amount after tax 
        System.out.println("change owed = " +  changeBack);
      

       
          //creating varible for the amount of change and cash to give to the customer 
        double qrtBack = change(cash, amountAfterTax) / quarter;
        double nickleBack = change(cash, amountAfterTax) / dime;
        double dimeBack = change(cash, amountAfterTax) / nickel;
            
        double fiveBack = change(cash, amountAfterTax) / fiveBill;
        double tenBack = change(cash, amountAfterTax) / tenBill;
        double twentyBack = change(cash, amountAfterTax) / twentyBill;
        double fifthyBack = change(cash, amountAfterTax) / fifthyBill;
        double hundoBack = change(cash, amountAfterTax) / hundredBill;
       
        
             //if statment to break the loop when the coin method is chosen  
       if(input1.equalsIgnoreCase(coinMethod)){
            System.out.println("change due to the customer can be broken down into");
            System.out.println(""); //blank space
            System.out.println("give " + qrtBack + " quarters back"); 
            System.out.println(""); //blank space
            System.out.println("give " + nickleBack + " Nickles back :)");
            System.out.println(""); //blank space
            System.out.println("give " + dimeBack + " Dimes back");
        break;
       }
      //else if statment for the cash method 
       else if(input1.equalsIgnoreCase(cashMethod)){
            System.out.println("change due to the customer can be broken down into");
            System.out.println(""); //blank space
            System.out.println("give " + fiveBack + " Five Dollar Bills"); 
            System.out.println(""); //blank space
            System.out.println("give " + tenBack + " Ten Dollar Bills");
            System.out.println(""); //blank space
            System.out.println("give " + twentyBack + " Twenty Dollar Bills");
            System.out.println(""); //blank space
            System.out.println("give " + fifthyBack + " Fifthy Dollar  Dollar Bills ");
            System.out.println(""); //blank space
            System.out.println("give " + hundoBack + " Hundred Dollar Bills ");
        break;
        }
    }
    }
//create method 
     public static double change(double amountGiven, double cost)
    {
        double amountDue = ( (double)((int) Math.round((amountGiven - cost)*100)) / 100.00 ); 
        return amountDue; 
    }
     //now time for the tax method  hahhaha :( me no like tax
        public static double tax(double cost) {
            double tax = cost * 0.13;
            double taxCost = tax + cost;
            double amountAftTax = ( (double)((int) Math.round((taxCost)*100)) / 100.00);
            return amountAftTax;
            
        }
        
}
