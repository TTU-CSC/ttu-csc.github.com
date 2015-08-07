---
layout: post
title:  "Lab 8: Lockbox"
date:   2015-07-19 13:05:30
categories: docs
---

For this lab, we want to design a simple safe, which will use a display, some buttons, a piezo, and an LED. 

This is the circuit layout for this week, excluding the LCD shield, of course:
![Lab 8 diagram]({{site.url}}/images/lab_8.jpg)

The end result should be that the display starts out showing "UNLOCKED" on the screen, with the red LED on and the green one off, since this is a dangerous state to be in -- anyone could take our stuff! When the user presses "SELECT" it will lock the safe, which involves printing "LOCKED" on the screen, as well as turning on the green LED and turning off the red one. The next time SELECT is pressed, it will ask for a 4-digit code to be entered. If the code is correct, it will return to the unlocked state. If the code is wrong, it will print a message on the screen saying

          STOP!
     HACKER DETECTED

and then begin flashing the red LED quickly and running the piezoelectric buzzer. The green LED should stay on to indicate that the items in the lockbox are still safe. After about 5 seconds, it should stop and return to the locked state, ready for someone to try to unlock it again.

To do this, you will want to use an array to store the button sequence. To do this, simply initialize an array like so:

    int passwd = { btnUP, btnLEFT, btnLEFT, btnUP };

or whatever sequence you would like. In order to check the password the user enters against it, we will need an array to hold their attempt (that way they don't know which button push was wrong).

    int attempt[4];

Then we just need a for loop

    for (int i = 0; i < 4; i++)
    {
    	//store values into the attempt array here
    }

followed by another one that will check the values:

    for (int i = 0; i < 4; i++)
    {
    	//check each value in attempt against the passwd array
    }

if one of the values doesn't match up, then we should `break` out of the loop and start the 5-second error sequence before returning to the locked state.