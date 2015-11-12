#COMSC 1033 Homework 9 - Methods and Loops Addition Game Rewrite

##Intro

Rewrote Addition Game program from homework 6 using method calls and loops. 

##Outline

<ul>
<li>Import scanner</li>

<li>Call addition game method</li>

<li>Set up loops for number of rounds and to keep score</li>

<li>Use boolean expression to determine loop execution</li>

<li>Obtain user input</li> 

<li>Return results</li>
</ul>

##References

<li>Liang, Y. (2014). Introduction to Java programming: Comprehensive version (Tenth ed.).</li>


##Code

''' java

import java.util.Scanner;

public class AdditionGame_Rewrite {
	public static void main(String[] args) {
		//System.out.println("Hello class.");
		
		//Call the addition game method.
		AdditonGameMethod();
	}
	public static void AdditonGameMethod() {
		//System.out.println("Inside the addition game method.");
		
		int hardness = 5;
		int hardnessStep = 2;
		int score = 0;
		
		// Set up my for loop to go through the number of rounds
		int numberOfRounds = 3;
		for(int roundNumber = 1; 
		roundNumber <= numberOfRounds;  
		roundNumber = roundNumber + 1){
			//System.out.println("Inside the for loop. Round: " + roundNumber);
			System.out.print("Round " + roundNumber + " of " + numberOfRounds + ". ");
			boolean isAnswerCorrect = getAndCheckStudentAnswer(hardness);
			if(isAnswerCorrect){
				System.out.print("Your score was " + score + " and is now ");
				score = score + hardness;
				System.out.print(score + ". ");
				
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + hardness + " and is now ");
					hardness = hardness * hardnessStep;
					System.out.println(hardness + ".");
				}
			}else{
				System.out.print("Your score is " + score + ". ");
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + hardness + " and is now ");
					if(hardness>5){
						hardness = hardness / hardnessStep;
					}
					System.out.println(hardness + ".");
					
				}
				
			}
		}
		System.out.print("\nThe game is complete. ");
		System.out.println("Your final score was " + score );
	}
	
	public static boolean getAndCheckStudentAnswer(int hardness) {
		//System.out.println("Inside get and check student answer method.");
		int number1 = (int)(Math.random()*hardness);
		int number2 = (int)(Math.random()*hardness);
		System.out.print("Add " + number1 + " and " + number2 +": ");
		//Scanner input = new Scanner(System.in);
		//int studentAnswer = input.nextInt();
		Scanner get = new Scanner(System.in);
		int studentAnswer = get.nextInt();
		if(studentAnswer == (number1 + number2)){
			System.out.print("Correct. ");
			return true;
		}else{
			System.out.println("Nice try, but the correct answer was " 
					+ (number1 + number2) + ".");
			return false;
		}
	}
}

'''

##Console Output


```
Round 1 of 3. Add 3 and 4: 7
Correct. Your score was 0 and is now 5. Your hardness was 5 and is now 10.
Round 2 of 3. Add 6 and 7: 13
Correct. Your score was 5 and is now 15. Your hardness was 10 and is now 20.
Round 3 of 3. Add 18 and 6: 24
Correct. Your score was 15 and is now 35.
--------------------------------------------
Round 1 of 3. Add 3 and 3: 7
Nice try, but the correct answer was 6.
Your score is 0. Your hardness was 5 and is now 5.
Round 2 of 3. Add 1 and 1: 3
Nice try, but the correct answer was 2.
Your score is 0. Your hardness was 5 and is now 5.
Round 3 of 3. Add 2 and 1: 4
Nice try, but the correct answer was 3.
Your score is 0. 
The game is complete. Your final score was 0

```

##Command Prompt History


```

```

##Summary

Like I said before, the hardest part about this assignment and about most of the ones I've had trouble with in the past 
is actually picturing how to do the things I'm supposed to actually do. After this assignment I feel comfortable with using
Git, creating and switching between branches, and merging work done on different branches. Or at least it makes more sense 
to me after doing this assignment. I actually kind of get the significance of using a website like github. Before I was pretty 
uncomfortable about creating and switching between different branches