# FooCorp
package foocorporation3;

import java.util.Scanner;

public class FooCorporation3 {
    
public static void breakLine() {
   System.out.println(); 
}    
    
public static double payCalc(double basePay, double hoursWorked) {
        double error = 0.00;
        if (basePay >= 8.00 && hoursWorked <= 40)
            {System.out.printf("$%.2f\n", (basePay * hoursWorked));}
        else if (basePay >= 8.00 && (hoursWorked > 40 && hoursWorked <= 60))
            {System.out.printf("$%.2f\n",(((hoursWorked % 40) * (basePay * 1.5)) + ((hoursWorked - (hoursWorked % 40)) * basePay)));} 
        else
            System.out.println("Error.");
            return error;
    }
    

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        boolean exit = false;
        
    /* Summary of Rules:
        - Employees receive (HOURS WORKED) * (BASE PAY) up to 40 HOURS each week.
        - HOURS OVER 40, (BASE PAY) * (1.50)
        - (BASE PAY) CANNOT be under $8.00, print error if it is
        - If HOURS WORKED is greater than 60, print error.
        
       EMPLOYEE # | BASE PAY | HOURS WORKED | 
       Employee 1 | $7.50    | 35
       Employee 2 | $8.20    | 47
       Employee 3 | $10.00   | 73                                       */
       
    while (!exit)
    {
     int n = 1;   
     System.out.println("Please enter employee " + ++n + "'s base pay and hours worked, separated by a space.");
     double employeeBasePay = input.nextDouble();
     double employeeHoursWorked = input.nextDouble();
        breakLine();
     
     payCalc(employeeBasePay, employeeHoursWorked);
        breakLine();
     
     System.out.println("Would you like to exit? 1 for YES, 2 for NO");
     double i = input.nextDouble();
     
     if (1 == i)
     {
         exit = true;
     } else exit = false;
     
    }
    
}
}
