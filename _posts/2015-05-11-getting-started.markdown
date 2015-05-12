---
layout: post
title:  "Getting started with Arduino!"
date:   2015-05-11 12:37:30
categories: docs
---

To get started with Arduino, you need to download and install the Arduino IDE.

Debian / Ubuntu Linux:

1. Open a terminal and type `sudo apt-get install arduino`
  1. The version contained in the repos is likely *heavily* outdated, but it installs all needed dependencies.
2. Next, [download][ArduinoIDE] the Linux version appropriate to your CPU architecture.
3. Use `tar -xvf arduino-*-linux*.tar.xz` or some other method to extract it in a convenient location.
4. Using a terminal, `cd` into the arduino directory, and run `./arduino` to start the IDE.

Mac OS X:

1. [Download it from here][ArduinoIDE]
2. Move the Arduino.app that is extracted from the zip into the Applications folder
3. No step three here either.

Windows:

1. [Download it from here][ArduinoIDE]
2. Install it like any other program.
3. You will probably need to follow [these instructions][Instructions] to install additional drivers.
  1. [This page][ScreenshotTutorial] is slightly outdated, but could be helpful.

Now that the Arduino IDE is installed, it is time to make sure everything is working.

1. Open the IDE
2. Go to File -> Examples -> 01.Basics -> Blink
3. Click the button in the toolbar that looks like an arrow facing to the right.

If your Arduino IDE is configured correctly and your Arduino is plugged in, you should have an LED blinking on it now.

[ArduinoIDE]:         http://www.arduino.cc/en/Main/Software
[Instructions]:       http://www.arduino.cc/en/Guide/Windows#toc4
[ScreenshotTutorial]: http://www.arduino.cc/en/Guide/UnoDriversWindowsXP
