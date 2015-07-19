---
layout: post
title:  "Lab 9: Music Box"
date:   2015-07-19 13:10:30
categories: docs
---

For this lab, we want to design a simple thermostat for an air conditioner. We're going to use the tri-color LED, a temperature sensor, and the LCD Shield.

Since this is an analog temperature sensor, you simply need to do an `analogRead` to see how the temperature is affecting the voltage output. The formula to convert the voltage to temperature is simple:  `Temperature in °C = (millivolts - 500) / 10`. To get `millivolts`, `millivolts = (5000.0/1024.0) * analogRead(some_pin_number);`

Pulse Width Modulation, PWM, is a technique for imitiating an analog output. Since an output pin can *only* ever be HIGH or LOW, you cannot ouput 3.5 volts, for instance. However, with PWM, you can *average* 3.5 volts on a particular output pin. This works by turning the output on and off *really fast*, and leaving it on for a different length of time than you leave it off. For 2.5 volts, it would just turn it on and off really quickly, but for 3.5 volts, it will stay "on" for longer than it stays "off", and so if you averaged the output value it would be 3.5 volts. This lets us adjust the brightness of an LED in software. For Arduino, in fact, the technique is called `analogWrite`, and it works on pins 3, 5, 6, 9, 10, and 11. So, for this lab, make sure that the red and blue cathodes of your tri-color LED are connected to two of those pins.

`analogWrite` is defined as `void analogWrite(pin, value)`, where `value` is an 8-bit value, 0 to 255. 255 is 5-volts, and 0 is 0-volts.

We will assume that the fan is always circulating air in the building. What we need to control is the temperature of that air. We will start out by targeting 70 degrees Fahrenheit, and the LCD display should always show the currently targeted temperature, along with the current temperature. The up and down arrow keys on the LCD shield will control the target temperature, moving it up and down.

If the temperature in the room is greater than the target temperature, we want to start lighting up the blue LED, signifying that we're pumping cold air into the room. If it is already colder in the room, then we want to light up the red LED, heating the room. The formula for the analog output value that we're writing to these LEDs should be calculated as such: `int analogVal = (target temperature - current_temperature) * 51;` This will mean that if the two temperatures are 5 degrees apart, we are turning on either the blue LED or the red LED fully. You should check the value of `analogVal`. If it is less than zero, flip the sign so it is positive and `analogWrite` it to the heater. If it is greater than zero, `analogWrite` it to the A/C. **Always** make sure the value is less than 256 before using `analogWrite` with it. If it is greater than 255, then set it to 255. If it is less than -255, set it to -255, but make sure that you are planning to flip the sign from negative to positive before writing it as well.
