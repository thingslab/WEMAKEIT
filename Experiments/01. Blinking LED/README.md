# Experiment 1: Blinking an LED

## Introduction

LEDs are small, powerful lights that are used in many different applications. To start off, we will work on blinking an LED, the Hello World of microcontrollers. That's right - it's as simple as turning a light on and off. It might not seem like much, but establishing this important baseline will give you a solid foundation as we work toward more complex experiments.

**Learn:** Digital output, timing (delay)  
**Platform:** Breadboard / ESP32 DevKit  
**Output:** Single LED blink circuit

## Parts Needed

You will need the following parts:

- 1x ESP32 DevKit + USB cable
- 1x Breadboard
- 1x LED
- 1x 330Ω Resistor
- 2x Jumper Wires

## Suggested Reading

Before continuing on with this experiment, we recommend you be familiar with the concepts in the following tutorial:

- Light-emitting Diodes - Learn more about LEDs!

## Hardware Hookup

Ready to start hooking everything up? Check out the diagram and hookup table below, to see how everything is connected.

**Polarized Components**

Pay special attention to the component's markings indicating how to place it on the breadboard. Polarized components can only be connected to a circuit in one direction.

**Please note: Pay close attention to the LED. The negative side of the LED is the short leg, marked with a flat edge.**

Components like resistors need to have their legs bent into 90° angles in order to correctly fit the breadboard sockets. You can also cut the legs shorter to make them easier to work with on the breadboard.

### Wiring Diagram

- Connect the ESP32 DevKit GND to the breadboard ground rail.
- Connect one leg of the 330Ω resistor to GPIO 13 on the ESP32.
- Connect the other leg of the resistor to the anode (long leg) of the LED.
- Connect the cathode (short leg) of the LED to the ground rail on the breadboard.

## Open Your First Sketch

Open up the Arduino IDE software on your computer. Coding in the Arduino language will control your circuit. Ensure you have the ESP32 board support installed.

Copy and paste the following code into the Arduino IDE. Select the ESP32 DevKit board, choose the correct port, and hit upload!

```cpp
/*
 * ESP32 Blinking LED Example
 * Turn an LED on for one second, off for one second, and repeat forever.
 */

void setup() {
  pinMode(13, OUTPUT);  // Set GPIO 13 as output
}

void loop() {
  digitalWrite(13, HIGH);  // Turn on the LED
  delay(1000);             // Wait for one second
  digitalWrite(13, LOW);   // Turn off the LED
  delay(1000);             // Wait for one second
}

/*
 * Try changing the 1000 in the above delay() functions to different numbers and see how it affects the timing.
 * Smaller values will make the loop run faster.
 *
 * Other challenges:
 *   - Decrease the delay to 10 ms. Can you still see it blink? Find the smallest delay that you can still see a blink. What is this frequency?
 *   - Modify the code above to resemble a heartbeat.
 */
```

## Code to Note

`pinMode(13, OUTPUT);`

Before you can use one of the ESP32's pins, you need to tell it whether it is an INPUT or OUTPUT. We use a built-in function called `pinMode()` to do this.

`digitalWrite(13, HIGH);`

When you're using a pin as an OUTPUT, you can command it to be HIGH (output 3.3 volts), or LOW (output 0 volts).

## What You Should See

You should see your LED blink on and off. If it isn't, make sure you have assembled the circuit correctly and verified and uploaded the code to your board, or see the troubleshooting section.

## Real World Application

Almost all modern flat screen televisions and monitors have LED indicator lights to show they are on or off.

## Troubleshooting

### LED Not Lighting Up?

LEDs will only work in one direction. Try taking it out of your breadboard, turning it 180 degrees, and reinserting it.

### Program Not Uploading

This happens sometimes; the most likely cause is a confused serial port. You can change this in Tools > Serial Port > in the Arduino IDE. Also, ensure the ESP32 board is selected in Tools > Board.

### Still No Success?

A broken circuit is no fun. Check your wiring, ensure the ESP32 is powered correctly, and verify the code.</content>
<parameter name="path">Experiments/01. Blinking LED/README.md