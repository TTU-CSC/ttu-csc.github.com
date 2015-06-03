---
layout: post
title:  "Lab 3: Conditional Logic"
date:   2015-06-01 14:35:30
categories: docs
---

In this lab, we'll be adding two pushbuttons to the previous lab and using them to affect the output *conditionally*. (i.e. according to various rules)

This is the circuit layout for this week:
<Insert fritzing diagram here>

We're now connecting button 1 to `pin 2` and button 2 to `pin 3`.

Background
==========

In Conditional Logic, the goal is to make decisions based on information, rather than blindly doing the same thing over and over. In C++, there are a variety of logical operators. Here, we'll look at a subset of those known as relational operators.

    == equal to
    != not equal to
    <  less than
    <= less than or equal to
    >  greater than
    >= greater than or equal to

Each of these is used in conjunction with two *expressions*. Let's look at an example:

    int numButtonsPushed = 0; //declare an integer named "numButtonsPushed" that has a value of 0.
    //we're going to use this integer to count how many buttons are pushed.
    
    if (digitalRead(2) == HIGH)  // "if digitalRead(2) is equal to HIGH"
    {  // could also be said to say "if pin 2 is equal to HIGH" or "if pin 2 is on"
        numButtonsPushed = numButtonsPushed + 1; // then let numButtonsPushed become the value of numButtonsPushed plus 1.
    }
    if (digitalRead(3) == HIGH) // "if digitalRead(3) is equal to HIGH"
    {
        numButtonsPushed = numButtonsPushed + 1; //then let numButtonsPushed become the value of numButtonsPushed plus 1
    }
    
    if (numButtonsPushed == 2) // "if numButtonsPushed is equal to 2"
    {
        // do some stuff only if both buttons are pushed
    }
    else if (numButtonsPushed > 0) // "if numButtonsPushed is greater than 0"
    {
        // do some stuff if at least one button is pushed
    }
    else if (analogRead(0) <= 500) // "if analogRead(0) is less than or equal to 500"
    {
        // do some stuff if the potentiometer is less than about halfway
    }
    else
    {
        // do some stuff if no button is pushed
    }

These relational operators allow your code to make decisions and therefore behave differently in different circumstances.

The Lab (part 1)
========

In part 1, we're going to use basic conditional logic to change the behavior of our system from the previous lab. At the end of the last lab, we were taking the analog value, dividing it by 40, and then adding 20 to it. Let's do the math! The range of the analog input is normally `0 <= x <= 1023`, where `x` is the current value of the analogRead() function.

`(0 <= x <= 1023) / 40` becomes `0 <= x <= 25`, mathematically. If we do `(0 <= x <= 25) + 20`, we get `20 <= x <= 45` as the range of our analog input after the math.

So, taking our `loop` code from last lab, let's calculate our analog value (`analogRead(0) / 40 + 20`) and then *use that* as part of a conditional statement. In the last lab, we were turning both the LED and the Piezo "on", waiting 10ms, and then turning both off again and waiting by a number of milliseconds equal to the calculated analog value. Let's move that code inside an if statement. Let's start out by saying `if` the calculated analog value is greater than 30, then we want to use the LED and the Piezo. This way, if the value is less than 30, we won't hear any buzzer or see the LED flashing.

The next thing we want to do is add an `else if` to our `if` statement. What we're going to do is make the LED blink at a steady rate of twice per second if the analog value *wasn't* greater than 30, and if button 1 is pushed. Remember, statements inside an `else if` block will *only* execute *if* their condition is true *and* if the previous `if` block did *not* execute, so we won't need to refer to the analog value at all in our `else if` block. Got it? Also, remember `digitalRead` is the function that we use to read buttons and other *digital* values.
