package ProjectCSI201.java;

import java.util.Random;
import java.util.Scanner;

public class ProjectCSI201 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int userScore = 0;
        int computerScore = 0;

        String[] choices = {"rock", "paper", "scissors"};

        System.out.println("=== Project 201: Rock, Paper, Scissors ===");

        while (true) {
            System.out.print("\nEnter rock, paper, or scissors: ");
            String userChoice = scanner.nextLine().trim().toLowerCase();

            // Input validation
            if (!userChoice.equals("rock") && 
                !userChoice.equals("paper") && 
                !userChoice.equals("scissors")) {
                System.out.println("Invalid input. Try again.");
                continue;
            }

            // Computer choice
            String computerChoice = choices[random.nextInt(3)];

            System.out.println("You chose: " + userChoice);
            System.out.println("Computer chose: " + computerChoice);

            // Determine winner
            if (userChoice.equals(computerChoice)) {
                System.out.println("It's a tie!");
            } else if (
                (userChoice.equals("rock") && computerChoice.equals("scissors")) ||
                (userChoice.equals("scissors") && computerChoice.equals("paper")) ||
                (userChoice.equals("paper") && computerChoice.equals("rock"))
            ) {
                System.out.println("You win!");
                userScore++;
            } else {
                System.out.println("Computer wins!");
                computerScore++;
            }

            // Display score
            System.out.println("Score -> You: " + userScore + " | Computer: " + computerScore);

            // Replay option
            System.out.print("\nPlay again? (yes/no): ");
            String answer = scanner.nextLine().trim().toLowerCase();

            if (!answer.equals("yes")) {
                System.out.println("\nFinal Score:");
                System.out.println("You: " + userScore + " | Computer: " + computerScore);
                System.out.println("Thanks for playing Project 201!");
                break;
            }
        }

        scanner.close();
	}

}
