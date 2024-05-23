## Lab Report 4

![image](https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/37314862-5f10-49a0-aafe-e7410539adc6)

Unfortunately, I encountered an error when using my ssh key and wasn't able to connect github to my ssh key. I will still try to provide what I think I would do but won't be able to provide screenshots until I get this fixed. I'll eat the 1 or 2 :(. 

Step 4:

I just typed in `ssh smai@ieng6.ucsd.edu` to log into the ieng6 engine. `<command> + <control> + <shift> + <4>` to ss and output here.


Step 5:

For step 5, I typed in `git clone git@github.com:KawsAndEffect/lab7.git`. This clones my fork of lab7 using the ssh url. I `<command> + <control> + <shift> + <4>` to grab a ss of the input and output of the command being run in terminal and paste it here.


Step 6:

First, we `cd lab7` to get into our lab7 clone. Then I used `ls` to see our files and what we have going on in lab7. Then I run `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` to compile our test files. Next to run it, I ran `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore test.sh`. This may be unnecessary and I can just run bash test.sh to run the tests. Then I would `<command> + <control> + <shift> + <4>` and screengrab the output of failed tests. 


Step 7:

First, I'd run `vim ListExamplesTests.java` then I would use the arrow keys to move my cursor down since I prefer it over `<h><j><k><l>`. So I would `<down><down><down>` to the first test that failed from Step 6. After reading, I found out I actually needed to change `BLANK`. Oh wow, I needed to delete this line here? I positioned my cursor to the need to be deleted line and ran this command `dd` and now I got rid of the error for this test. After that, we `<command> + <control> + <shift> + <4>` and screengrab some before and afters of our edits.


Step 8:

To run the tests, I need to exit out of the vim window! Let's exit and save using `:wq then <Enter>`. Once we back into our ssh terminal, we run our tests from before `Keys pressed: <up><up><up><up><enter>, <up><up><up><up><enter> The javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java command was 4 up in the search history, so I used up arrow to access it. Then the java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore test.sh command was 4 up in the history, so I accessed and ran it in the same way.` After that, we `<command> + <control> + <shift> + <4>` and screengrab out successful tests! WOOOOO!


Step 9:

Now that we fixed our test errors, we can stage, commit, and push to our GitHub account. So we start with `git add .` to stage all changes made. Then we commit our changes by running `git commit -m Successfully fixed test errors in ListExamplesTests.java`. Finally we run `git push` to push all our commited changes to our GitHub repository. We `<command> + <control> + <shift> + <4>` our `git` commands in the terminal and its outputs and then show that the changes show in our GitHub repo. 

