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

<img src="/blog/images/vsc_ddmenu.jpeg" alt="VSC dropdown menu" width=500px>
<p style="font-size: 12px">Dropdown menu in Visual Studio Code that leads to debug tool</p>

Clicking the arrow will then open a menu with four options. The choice we want is “Python Debugger: Debug Python File.” This takes us to the “Run and Debug” screen in the side bar.

This also opens a small control panel that holds the options for our debugging.

<img src="/blog/images/debug_panel.jpeg" alt="Debug panel" width=500px>
<p style="font-size: 12px">Visual Studio Code debugging tool panel. Holds buttons for different debugging functions.</p>

This panel holds six buttons (the first two will be important for our process) which will help us debug our program.

Before we use these buttons, we must establish a breakpoint (or the section of code that will be run). This is done by hovering over the space next to the line number and clicking on the faint red circle that appears.This is the breakpoint and it will run code that succeeds the line the breakpoint is on for debugging.

The first button that looks like a pause button (two blue lines) runs the code from the breakpoint on and the second button (curved arrow over a dot) will run a line of code every time it is clicked. This allows you to see how the code operates on each line (Each active line will be highlighted yellow and have a small yellow indicator next to the line number). 

On the left of your screen, you will see the variables in your code. These will change as the program progresses. 

<img src="/blog/images/var_panel.png" alt="Variable panel in VSC" width=500px>
<p style="font-size: 12px">Visual Studio Code variable panel. Shows variables in the program and how they change as the program runs.</p>


These are the essential tools to my debugging experience, but there are other areas of Visual Studio Code debugging to explore.

## Debugging Challenges

For this assignment I had to debug 4 sets of code. I had to run the code to make sure that it made the expected output, identify and explain any issues the program had, and modify the code to ensure it meets its expected output and explain my modifications. 

The first set of code I debugged was:

```python
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == "":
       count += 1

print(count)
```

The purpose of this program was to count how many spaces were in a given string. The only issue in the code was in the if statement as it ran when the string was empty and not for spaces.

I solved this issue by putting a space in the quotation marks.

You can see the corrected program below:

```python
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == " ":
       count += 1

print(count)
```

The second program I had to debug can be seen below:

```python
print("give me a number")
n = input()

for num in range(1, n):
    if num % 2 < 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

This code was meant to determine whether numbers 1 to n were even or odd.

I found three problems with the code:

<ol>
<li>There was a type error in line 4 because n was a string and was a range argument so the loop could not iterate properly. </li>
<li>The if statement ran if the remainder of the number divided by 2 was greater than 0 for the number to be even</li>
<li>The program needed to iterate through the numbers from 1 to the input, and the input number would be excluded.</li>
</ol>

I solved these issues by:

<ol>
<li>Make the user input an integer using the int function to allow the loop to iterate.</li>
<li>Changing the if statement less than sign to an equality sign (==) so if the remainder of the current number divided by 2 was zero the number would be printed as even.</li>
<li>Adding a "+ 1" after the n in the range function  so when the program ran the loop would iterate the user’s input as well.</li>
</ol>

The corrected code is below:
```python
print("give me a number")
n = int(input())

for num in range(1, n + 1):
    if num % 2 == 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
```

The third program I had to debug was made to calculated the factorial of a number.

```python
num = int(input("Enter an integer: "))

if num < -1:
  print("No negative numbers.")
else:
  result = 1
  for i in range(1, num):
    result *= i   

  print("Factorial of " + num + "is" + result)
```

The two issues of the code were:

<ol>
<li>The range function in the for loop excludes the user input from being iterated which means the factorial cannot be calculated properly as the number used is excluded from calculation.</li>
<li>the print statement cannot concatenate strings and integers so the sentence will not be printed.</li>
</ol>


I solved these issues by:

<ol>
<li>Adding a “+ 1” next to the “num” in the range function so the program will iterate through the user input and calculate the factorial properly as the number being excluded is ahead of the input.</li>
<li>Changing the plus signs in the print statement to commas so the print statement would print the strings and integers next to each other without concatenating them.</li>
</ol>

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
<p style="font-size: 12px">One of the programs I had to debug. It is supposed to allow users to input a password with three tries. Holds several logic errors.</p>

This program was meant to ask the user for the password and give them three attempts to do so. 

This program's issues were logic errors (when a program does not run as intended, ie a program that is meant to add numbers subtracts them)

The issues I found were:

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

These changes allowed the program to run as stated and you can see the corrected program below:

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

I also wonder how debugging tools may develop in the future to make the process easier. How will these new tools be developed? How widespread will they be? what problems will they solve or what things may become easier?

I imagine that AI could be used to highlight different problems, possible solutions, and  apply the soulution itself. It could also possibly be used to have more control over what sections of code are run. Maybe, it could be used to optimize the program by working with the purpose of the program internally and suggest edits to improve function. 

I think there is always room to grow and technology is one area where growth is always occuring, and I wonder how debugging will change in the future.
