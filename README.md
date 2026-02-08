# Simple_Calculator_program
This is my first ever small project code in java which is Simple Calculator where i tried to handle the input edge cases like if input is other than 0 or string type and then followed by conditions.
import java.util.*;
class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double n = 0,m = 0;
        double res = 0;
         System.out.println("Enter first number: ");
         boolean validInput = false;
         while(!validInput){
        try{
            n = sc.nextDouble();
            validInput = true;
            System.out.println("You entered num : "+n);
        }
        catch(InputMismatchException e){
            System.out.println("Error! Please enter the valid number");
            sc.next();
        }
     }
      System.out.println("Enter the value of m: ");
      validInput = false;
      while(!validInput){
        try{
            m = sc.nextDouble();
            validInput = true;
            System.out.println("You entered num : "+m);
        }
        catch(InputMismatchException e){
            System.out.println("Error! Please enter the valid number");
            sc.next();
        }
     }
     System.out.print("Enter operation (+,-,*,/,%): ");
     char operator = sc.next().charAt(0);
     boolean validation = true;
     
     switch(operator){
         case '+':
             res = n + m;
             break;
         
         case '-':
             res = n - m;
             break;
        case '*':
            res = n * m;
            break;
        case '%':
            if(m == 0){
                System.out.println("Error!! Can't be divided with zero!");
                validation = false;
            }
            else{
            res = n % m;
            }
            break;
        case '/':
            if(m == 0){
                System.out.println("Error!! Can't be divided with zero!");
                validation = false;
            }
            else{
            res = n / m;
            }
            break;
        
        default:
             System.out.println("Invalid operator!");
             validation = false;
     }
     if(validation){
     System.out.println("Result: "+res);
     }
    }
}
