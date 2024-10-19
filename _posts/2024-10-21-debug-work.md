# One for The Bug: A Debugging Experience

## Introduction

I had my first formal experience debugging code recently. I learned the different tools for debugging code, how these tools can help me, and develop new skills. I found this experience intriguing as I had solved issues with my code but had never formally debugged. 

## What is debugging?

First off, what is debugging? Debugging is the process of finding issues or errors and fixing them. The term reportedly originated in 1947 when Admiral Grace Hopper (she is an interesting person and you should look her up) and her associates found a moth in the Mark II computer that impeded its function. 

Debugging can be done in many different ways such as going through manually and finding issues, using print statements, researching different errors, externalizing the problem, etc. 

Specifically, I will be writing about using the internal debugging tools that code editors have. Since I use Visual Studio Code, I will be discussing their debugging tools as I have used them.

## A Guide to Visual Studio Code Debugging

Let's get into how Visual Studio Code debugging tools work:

First, you must access the debugging tool.

This is done by clicking the down arrow next to the run button near the top of the screen.

<img src="images/vscddmenu.jpeg" alt="menu" height=200px>

Click the arrow will then open a menu with four options. The choice we want is “Python Debugger: Debug Python File.” This takes us to the “Run and Debug” screen on the side bar.

This also opens a small control panel that holds the options for our debugging.

<img src="images/debug_panel.jpeg" alt="menu" width=200px>

This panel holds six buttons (the first two will be important for our process) which will help us debug our program.

Before we use these buttons, we must establish a breakpoint (or the section of code that will be run). This is done by hovering over the space next to the line number and clicking on the faint red circle that appears.This is the breakpoint and it will run code that succeeds the line the breakpoint is on for debugging.

The first button that looks like a pause button (two blue lines) runs the code from the breakpoint on and the second button (curved arrow over a dot) will run a line of code every time it is clicked. This allows you to see how the code operates on each line (Each active line will be highlighted yellow and have a small yellow indicator next to the line number). 

On the left of your screen, you will see the variables in your code. These will change as the program progresses. 

These are the essential tools to my debugging experience, but there are other areas of Visual Studio Code debugging to explore.

Debugging Challenges

For this assignment I had to debug 4 sets of code. I had to run the code to make sure that it made the expected output, identify and explain any issues the program had, and modify the code to ensure it meets its expected output and explain my modifications. 

Below is the fourth program I had to debug:

```python
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1

    if password == "incorrect_password":
        print("Correct password!")
    else:
        print("Incorrect password")

    if attempts > 3:
        print("Too many attempts")
        break
```

This program was meant to ask the user for the password and give them three attempts to do so. 

I found three issues with the program:

<ol>
<li>The if statement in line 8 did not equal the password and allowed for an incorrect guess to be printed as correct.</li>
<li>The program still ran even if the user’s guess was correct, which was unnecessary.</li>
<li>The if statement in line 13 (the one for attempts) allowed the user to try to guess the password four times and not three. The condition was set to break the program only if the amount of attempts were greater than 3.</li>
</ol>

I solved these issues by:
<ol>
<li>Changing the if statement to print correct if the user’s guess equaled the password.</li>
<li>Adding a break statement to the above if statement to end the program when the password was correct.</li>
<li>Setting the if statement condition to when attempts equal three.</li>
</ol>

These changes allowed the program to run properly and you can see the corrected program below:

```python
attempts = 0
correct_password = "secret"

while True:
   password = input("Enter your password: ")
   attempts += 1

   if password == correct_password:
       print("Correct password!")
       break
   else:
       print("Incorrect password")
   if attempts == 3:
       print("Too many attempts")
       break
```

## Final Thoughts

I found the process of debugging code interesting. I think that it is a useful skill to learn and it is helpful when issues arise in programming. I am curious about how other code editor tools handle debugging and if there are any drastic differences between them. 

