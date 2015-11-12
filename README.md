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

```
import java.util.Scanner;

public class AdditionGame_Rewrite {
	public static void main(String[] args) {
		
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

```

##Console Output


```
Round 1 of 3. Add 2 and 2: 4
Correct. Your score was 0 and is now 5. Your hardness was 5 and is now 10.
Round 2 of 3. Add 6 and 8: 14
Correct. Your score was 5 and is now 15. Your hardness was 10 and is now 20.
Round 3 of 3. Add 5 and 13: 18
Correct. Your score was 15 and is now 35. 
The game is complete. Your final score was 35
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

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': 54r4hv
Password for 'https://54r4hv@github.com':
Everything up-to-date

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m "."
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git merge
Already up-to-date.

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git checkout dev
Switched to branch 'dev'
Your branch is up-to-date with 'origin/dev'.

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git merge master
Already up-to-date.

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m ".."
On branch dev
Your branch is up-to-date with 'origin/dev'.
nothing to commit, working directory clean

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git merge master
Already up-to-date.

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git merge dev
Updating 150507e..d801417
Fast-forward
 .classpath                     |   6 ++++
 .project                       |  17 ++++++++++
 README.md                      |   3 ++
 bin/AdditionGame_Rewrite.class | Bin 0 -> 2340 bytes
 src/AdditionGame_Rewrite.java  |  70 +++++++++++++++++++++++++++++++++++++++++
 5 files changed, 96 insertions(+)
 create mode 100644 .classpath
 create mode 100644 .project
 create mode 100644 bin/AdditionGame_Rewrite.class
 create mode 100644 src/AdditionGame_Rewrite.java

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m "..."
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': 54r4hv
Password for 'https://54r4hv@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/54r4hv/HW9.git
   150507e..d801417  master -> master

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git branch
  dev
* master

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m "almost done"
[master 99df952] almost done
 1 file changed, 141 insertions(+), 4 deletions(-)
 rewrite README.md (87%)

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': 54r4hv
Password for 'https://54r4hv@github.com':
Counting objects: 3, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.68 KiB | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To https://github.com/54r4hv/HW9.git
   d801417..99df952  master -> master

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m "more changes"
[master b0e5d46] more changes
 1 file changed, 3 insertions(+), 2 deletions(-)

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': 54r4hv
Password for 'https://54r4hv@github.com':
Counting objects: 3, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 311 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
To https://github.com/54r4hv/HW9.git
   99df952..b0e5d46  master -> master

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m "some more changes"
[master 58ad1c6] some more changes
 1 file changed, 1 insertion(+), 2 deletions(-)

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': 54r4hv
Password for 'https://54r4hv@github.com':
Counting objects: 3, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 305 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
To https://github.com/54r4hv/HW9.git
   b0e5d46..58ad1c6  master -> master

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m ","
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m "bleh"
[master c17d690] bleh
 1 file changed, 1 insertion(+), 2 deletions(-)

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': 54r4hv
Password for 'https://54r4hv@github.com':
Counting objects: 3, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 306 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
To https://github.com/54r4hv/HW9.git
   58ad1c6..c17d690  master -> master

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git add .

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git commit -m "a"
[master 636bc9d] a
 1 file changed, 1 insertion(+), 1 deletion(-)

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': 54r4hv
Password for 'https://54r4hv@github.com':
Counting objects: 3, done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 300 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
To https://github.com/54r4hv/HW9.git
   c17d690..636bc9d  master -> master

C:\Users\denise\Desktop\workspace\COMSC1033_HW9>
```

##Summary

Like I said before, the hardest part about this assignment and about most of the ones I've had trouble with in the past 
is picturing how to do the things I'm supposed to actually do. After this assignment I feel comfortable with using
Git, creating and switching between branches, and merging work done on different branches to my upstream branch. Or at least 
it makes more sense to me after doing this assignment. I also am slowly but surely gaining a better understanding of methods 
and loops as well.  