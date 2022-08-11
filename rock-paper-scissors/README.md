# Development rock-paper-scissors
just a simple game of rock paper scissors
import java.util.Scanner;
import java.lang.Math;
public class Game
{
    public static void main(String [] args)
    {
        Scanner inputstr = new Scanner(System.in);
        Scanner input = new Scanner(System.in);

        // Intitialising the counters
        int countwin = 0,countLose = 0, counter = 1,countDraw = 0,countInvalid = 0;
        System.out.print("\nscissors (0), rock(1), paper(2) (5 to terminate program): ");
        int choice = input.nextInt();

        //loop that will execute while choice of player is not 5
        while(choice != 5)
        {
            //intitialising the coputer choice with random number from 0 to 3 
            int comp = (int)(Math.random() * 3);
            
            // a series of if-eslse statements to determine the winner
            if(comp == 0 && choice == 1 )
            {
                System.out.println("\nThe computer is scissors. You are rock. You win");
                countwin++;
            }
            else if(comp == 1 && choice == 0 )
            {
                System.out.println("\nThe computer is rock. You are scissors. You loose");
                countLose++;
            }
            else if(comp == 1 && choice == 2 )
            {
                System.out.println("\nThe computer is rock. You are paper. You win");
                countwin++;
            }
            else if(comp == 2 && choice == 1 )
            {
                System.out.println("\nThe computer is paper. You are rock. You loose");
                countLose++;
            }
            else if(comp == 0 && choice == 2 )
            {
                System.out.println("\nThe computer is scissors. You are paper. You loose");
                countLose++;
            }
            else if(comp == 2 && choice == 0 )
            {
                System.out.println("\nThe computer is paper. You are scissors. You win");
                countwin++;
            }
            else if(comp == 2 && choice == 2 )
            {
                System.out.println("\nThe computer is paper. You are paper. It's a draw");
                countDraw++;
            }
            else if(comp == 1 && choice == 1 )
            {
                System.out.println("\nThe computer is rock. You are rock. It's a draw");
                countDraw++;
            }
            else if(comp == 0 && choice == 0 )
            {
                System.out.println("\nThe computer is scissors. You are scissors. It's a draw");
                countDraw++;
            }
            else
            {
                System.out.println("\nInvalid input. Play again");
                countInvalid++;
            }
            counter++;
            System.out.print("\nscissors (0), rock(1), paper(2) (5 to terminate program): ");
            choice = input.nextInt();
        }

        //printing out the scored of the game
        System.out.println("\nThe total number of games played is: " + counter );
        System.out.println("Your score is: " + countwin);
        System.out.println("The computer's score is: " + countLose);
        System.out.println("The total number of games that ended in a draw is: " + countDraw);
        if(countwin > countLose)
        {
            System.out.println("\nYou are the winner of the overall performance!!! Congradulations");
        }
        else if(countwin < countLose)
        {
            System.out.println("\nThe computer is the winner of the overall performance - _ - Better luck next time");
        }
        else
        {
            System.out.println("\nThe overall performance was a draw between you and the computer");
        }
    }
}

