# Lab Report 5

### Part 1: Debugging Scenario

*Student's Post:*

Post Type: Question
Post To: Instructors (all)
Select Folders: Skill Demo 4
Summary: Can't print the `hashed` object and its length.
Details:
Here is a screenshot of the error that I'm getting. I have tried to get to the initialization of `hashed` by setting a breakpoint at line 682 of `BCrypt.java`. Once I get there, and hit the breakpoint, I run `print hashed` and it returns saying that it is null. I tried to `step` to get to the next line all the way
to line 700 (which is way past the initialization of hashed object) but keep getting the null value. Not sure where to go from here. Any help is appreciated!
![image](https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/fc6f316e-d0bd-40ec-9ac0-bb9199e12181)

*TA's Response:*  

Hey student,
Can you try to set the breakpoint to the line after the initialization instead of before the initialization? Once you do this, you should be able to print the `hashed` object as well
as any of its properties.

Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.
<img width="820" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/9ec11062-a314-451c-b154-faeac20a6987">
So the bug was that we were setting the breakpoint before the initialization which means that where we stopped didn't have the hashed object initialized and so it didn't matter if
we used `step` afterwards. The breakpoint needed to be after initialization.

At the end, all the information needed about the setup including:

The file & directory structure needed
<img width="373" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/e874b0a3-ea33-474d-8e7c-f90ddbf4acf1">

The full command line (or lines) you ran to trigger the bug
`cd JBcrypt`
`javac -g Main.java BCrypt.java`
`jdb Main mypassword`
`stop at BCrypt:682`
`run`
`print hashed`
`print hashed.length`
`step`
`step`
`print hashed.length`

A description of what to edit to fix the bug
Change `stop at Breakpoint:682` to `stop at Breakpoint:685`


### Part 2: Reflection
I didn't know how to use vim or jdb at all. Coming from a data science background, I never had experience using either of them. I've heard of vim once before but thought it was just
an alternative IDE like VSCode, Sublime, Atom, etc. Another cool thing that I learned about was the filepath names, I really enjoyed that portion since I never really learned in depth
about filepaths. I didn't know all these small things like what `../subdirectory` or `./something` meant. It was very interesting learning about terminal commands like `cat`, `echo`,
`grep`, etc. Small things in the terminal that help out. 
