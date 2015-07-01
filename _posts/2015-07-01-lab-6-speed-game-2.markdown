---
layout: post
title:  "Lab 6: Speed Game (Part 2)"
date:   2015-07-01 14:44:30
categories: docs
---

It's time for another fun lab! For this lab, we're simply going to use the Arduino LCD Shield.

The goal of this lab is to build the speed game another way. The gameplay should be as follows:
- set the LCD to show some message indicating the players should wait before pushing a button.
- wait for a random (but still reasonable) amount of time
- set the LCD to show an exciting message to get users to push the button (like "GO!")
- when one user presses their button after this point, the LCD should show a message indicating both that the game is over and who won.
- wait 2 seconds, then start it all over.

The only new information you need is to be able to read the buttons on the LCD shield, but if you need to remember how to set it up and write to the LCD, feel free to [review the first tutorial]({% post_url 2015-05-11-getting-started %}).

To clear the LCD screen, simply say `lcd.clear()` and `lcd.setCursor(0, 0)`.

To read the buttons, we will use this code:

    uint8_t buttons = lcd.readButtons();
    if (buttons & BUTTON_UP) //note the bitwise AND (&), this is not the logical AND (&&)
    {
    	//the up button was pushedm, do something here.
    }

`BUTTON_UP` represents the up button, but other options include `BUTTON_DOWN`, `BUTTON_LEFT`, `BUTTON_RIGHT`, and `BUTTON_SELECT`.

I recommend using BUTTON_LEFT and BUTTON_RIGHT for the two user buttons, but you can use whichever ones seem most appropriate.

Good luck!