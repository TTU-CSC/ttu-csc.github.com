---
layout: post
title:  "Overview of CSC2101 Labs"
date:   2015-05-14 14:00:00
categories: docs
---

Throughout the semester, there will be a variety of labs. Here, we will provide an overview of each lab.

### [Lab 0: Getting Started]({% post_url 2015-05-11-getting-started %})
**Purpose:** To get the Arduino environment set up   
**Description:** Teaches you how to install the Arduino environment and use a basic program on the Arduino. You will also use the Arduino LCD shield to write messages to the world!

### [Lab 1: I/O]({% post_url 2015-05-12-lab-1-IO %})  
**Purpose:** Learn how to use a microcontroller to interact with the real world, through buttons and LEDs.  
**Description:** In this lab, you will construct a simple circuit that consists of a button and two LEDs. When the button isn't being pressed, one LED is on and the other is off. However, while the button is being pressed, the LEDs should switch state. This shows how to use one input, a button, and two outputs.

### [Lab 2: I/O with Analog and Arithmetic]({% post_url 2015-05-14-lab-2-IO-analog %})  
**Purpose:** This lab teaches you how to deal with analog inputs.  
**Description:** Analog inputs are signals that aren't just binary, 1 or 0. These inputs cover a range of values, defined by the *voltage* being sensed at the analog input. In this lab, you will use an analog input from a potentiometer to control a piezoelectric speaker's frequency of output. You will also do some arithmetic to make the system behave in a more pleasant way.

### [Lab 3: Conditional Logic]({% post_url 2015-06-01-lab-3-conditional-logic %})  
**Purpose:** Through this lab, you will learn to use more complex conditional logic effectively.  
**Description:** Conditional Logic is a tool you will use to connect different results to different limiting factors, known as conditions. *If* a user presses a button *and* a user has pressed the other button *then* we will turn on this LED.

### [Lab 4: Loops]({% post_url 2015-06-02-lab-4-loops %})  
**Purpose:** To familiarize you with a useful tool to cut down on writing the same code over and over.  
**Description:** A loop is a structure that allows you to have the same piece of code happen over and over until some condition is false. There are different kinds of loops, and this lab will show you why they are useful. 

<While button is not pressed, blink LED. For each LED, turn that LED on, then wait, then off.>

### Lab 5: Speed Game (part 1)  
**Purpose:** Learning to use loops in more depth.  
**Description:** Using two buttons, two normal LEDs, and the tri-color LED, you're going to build a game. The game will wait for a random amount of time, and then the tri-color LED will change from red to green. Whoever pushes their button first wins, and their LED turns on. The tri-color LED also changes to blue. After about two seconds, the game will reset, so the tri-color LED will go back to red, and both of the players' LEDs will turn off.  

### Lab 6: Speed Game (part 2)  
**Purpose:** To use loops to measure time elapsed.   
**Description:** Here, we will build the speed game from last time, but using the Arduino LCD Shield. The buttons on the shield will be used instead of the buttons from last time, and all of the LEDs will be replaced with the LCD. On the LCD, we want to show what state we're in, whether that's waiting on the random time to elapse, waiting on a user to push a button, or showing the end game screen. On the end game screen, we want to show who won and how long it took each user to push their button.  

### Lab 7: A/C unit  
**Purpose:** Responding to changing conditions iteratively. (PWM + loops)  
**Description:** We're going to simulate a thermostat, reading the temperature of the surrounding environment to decide whether we need to apply A/C or not, and how cold to make it. We will use an LED to represent the A/C unit, and we'll assume that the fan is on at all times. The more the A/C is on, the colder the air will be, so we'll be pulsing the LED, and the greater the percentage of time that the LED is on, the colder the air is that we're representing.

### Lab 8: Temperature logger  
**Purpose:** Learn about arrays  
**Description:** We want to store temperature readings in an array that the user can browse through. When they push the start button, we will record ten temperature readings, spaced one second apart. The user will then be able to scroll through them using the buttons on the LCD shield.  

### Lab 9: Music Box  
**Purpose:** Learn about structs  
**Description:** Using an array of structs that consist of a frequency and a length, students will play songs.  

### Lab 10: Weight sensor  
**Purpose:** Do something interesting and practical  
**Description:** Using the force sensitive resistor, students will first measure the weight of a reference item, like a nickel, and then they will measure the weight of items in terms of the reference. (like, item X weighs 5 nickels.)  

### Labs 11 and 12 will be free form.
