# MSP430 Reflex Game
A simple reflex game made for the MSP430.
<br>The initial version was taken from a school test with this assignment (translated from italian):
```
Using the device MSP430F5529 Launchpad and its hardware, create a "reflex-test" game.
The game mechanics will be as follows:
- Initially both LEDs are off
- When the player clicks the START button (P1.1) the red LED(P1.0) turns on, it will stay on for 5 seconds.
- When the 5 seconds written above terminate, the red LED turns off and the player should press the STOP button (P2.1) as soon as he can.

The program will measure the time between the led turning off and the button press and it will display those value as follows:
- If the measured time is less than 200ms, the green LED will turn on;
- If the measured time is between 200ms and 500ms both the green and the red LED will turn on;
- If the measured time is more than 500ms only the red LED will turn on;

There will be some error cases: if the STOP button is pressed before the 5 seconds timeout or if it doesn't get pressed in a certain time after the 5 seconds timeout the game ends with the red led on.
To return to the initial state and begin playing again the player will press the START button.
```

## State diagram
![Cannot find image](state_diagram.png?raw=true "Title")
All the states are explained further in the source file.

## MSPAPI
The game uses a tiny abstraction API that is implemented in `mspapi.h`.
It is a library created by me that replaces the redundant code that deals with pin setup (LEDs and buttons) and helps the developer in focusing more on the actual logic.
