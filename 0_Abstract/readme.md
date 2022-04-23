In this project we are going to use one of the features of ATmega32A to adjust the brightness of 1 Watt LED.
The method that is used to adjust the speed of  LED is PWM (Pulse Width Modulation).
This AVR Microcontroller PWM tutorial explains the PWM concept and generation of PWM in detail (You can also check this simple PWM generator circuit).
Consider a simple circuit as shown in figure.
In ATmega, for four PWM channels, we have designated four pins. We can only take PWM output on these pins only.
Since we are using PWM0 we should take PWM signal at OC0 pin (PORTB 3rd PIN). 
We are connecting the base of transistor to OC0 pin to drive the power LED. Here another thing is over four PWM channels, two are 8-bit PWM channels. We are going to use a 8-bit PWM channel here.
A capacitor is connected to each of the buttons to avoid bouncing. Whenever a button is pressed there will be some noise at the pin. Although this noise stabilizes in milliseconds. For a controller the sharp peaks before stabilization acts as triggers.
This effect can be eliminated either by software or hardware, for the program to be simple. We are using hardware method by adding debouncing capacitor.  
The capacitors nullify the effect of bouncing of buttons.
