# Sensors: Light and temperature

```package
core
radio
microphone
```

```template
basic.forever(function () {
    
})
```

```blocks
basic.forever(function () {
    
})
```
## Step 0 @showDialog
Hi! Today we'll learn how to measure light and temperature with the Micro:bit.
## Step 1 @showDialog
### Light and temperature sensors
The light sensor is located on the front of the Micro:bit. To learn more about this sensor, watch this [video](https://youtu.be/ii0U_FMr-Z4).
  
The temperature sensor is inside the Micro:bit processor. It measures temperature in degrees Celsius. There is a [video](https://youtu.be/mrHn8eZ9eqg) about this sensor, too.
## Step 2 @showDialog
### Measuring light and temperature
As we've already learned, the code blocks for sensors can be found inside the ``||input.input||`` folder. Today we'll use the ``||input.light level||`` and ``||input.temperature||`` blocks.
The round blocks return values from the sensors. This is how we can show light or temperature levels on the screen:
```block
basic.showNumber(input.temperature())
```
```block
basic.showNumber(input.lightLevel())
```
## Step 3 @showHint
### Measuring light
The ``||input.light level||`` block returns numbers from 0 to 255.
  - 0 means complete darkness
  - 255 means bright light  

Assemble the program, download it to the Micro:bit and try to find the lightest and darkest places in your home!
```blocks
basic.forever(function () {
    basic.showNumber(input.lightLevel())
})
```
## Step 3.5 @showHint
### Measuring light
Do numbers seem boring? We can show a bar graph instead!
The sensor measures light level readings between 0 and 255, so inside the ``||led.plot bar graph||`` block we can choose 255 to be the upper limit.
```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
})
```

## Step 4
### Check yourself!
Let's check to see if you remember what we learned earlier. Change the code so that the Micro:bit shows the light level when a button is pressed.

## Step 5 @showHint
### Measuring temperature
The ``||input.temperature||`` block returns temperature readings in degrees Celsius.  
Assemble the program and download it into the Micro:bit. Let's see how warm your home is!
```blocks
basic.forever(function () {
    basic.showNumber(input.temperature())
})
```

## Step 6 @showHint
### Additional project: a precision thermometer
In use, the device heats up, and this introduces an error in the thermometer readings. To make the readings more accurate, you can measure the temperature with another thermometer and change the program to be more correct.
```hint
In this example, the temperature of the device turned out to be
higher than the air temperature by 5 degrees:
```
```blocks
basic.forever(function () {
    basic.showNumber(input.temperature() - 5)
})
```
## Step 7 @showHint
### Additional project: Fahrenheit scale
In the United States, temperature is measured on the Fahrenheit scale. We can use mathematical formulas to show the temperature the way we want.
```hint
Temperature in Fahrenheit:
```
```blocks
basic.forever(function () {
    basic.showNumber(input.temperature() * 1.8 + 32)
})
```

## Step 8
### Now it's your turn!
As always, we have a challenge for you at the end! Write a program for a weather station that will show both light and temperature, in any form that works for you.

## Step 9 @showDialog
### Answers: Check for yourself!
```blocks
input.onButtonPressed(Button.A, function () {
    led.plotBarGraph(
    input.lightLevel(),
    255
    )
})
```
### Answers: Now it's your turn!
Here is one option for the program:
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("The temperature is ")
    basic.showNumber(input.temperature() * 1.8 + 32)
})
input.onButtonPressed(Button.B, function () {
    basic.showString("The light level is ")
    basic.showNumber(input.lightLevel())
})
```
## Step 8
Another lesson completed! To repeat, today we learned how to measure light and temperature using Micro:bit sensors. 
