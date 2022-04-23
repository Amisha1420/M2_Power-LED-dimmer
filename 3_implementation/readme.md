In ATmega, for four PWM channels, we have designated four pins. We can only take PWM output on these pins only. Since we are using PWM0 we should take PWM signal at OC0 pin (PORTB 3rd PIN).  As shown in figure we are connecting the base of transistor to OC0 pin to drive the power LED. Here another thing is over four PWM channels, two are 8-bit PWM channels. We are going to use a 8-bit PWM channel here.
A capacitor is connected to each of the buttons to avoid bouncing. Whenever a button is pressed there will be some noise at the pin. Although this noise stabilizes in milliseconds. For a controller the sharp peaks before stabilization acts as triggers. This effect can be eliminated either by software or hardware, for the program to be simple. We are using hardware method by adding debouncing capacitor.  
The capacitors nullify the effect of bouncing of buttons.
In ATMEGA there are couple of ways to generate PWM, they are:
1. Phase correct PWM
2. Fast PWM
Here we are going to keep everything simple, So we are going to use FAST PWM method to generate the PWM signal.
First to choose the frequency of PWM, This depend on application usually, for an LED any frequency greater than 50Hz would do. For this reason we are choosing the counter clock 1MHZ. So we are choosing no prescalar.  A prescalar is a number which is so selected to get a lesser counter clock. For example if the oscillator clock is 8Mhz, we can chose a prescalar of ‘8’ to get a 1MHz clock for counter. The prescalar is selected based on frequency. If we want more time period pulses we have to chose higher prescalar.
Now to get the FAST PWM of 50Hz clock out of the ATMEGA, we need to enable the appropriate bits in “TCCR0” register. This is the only register we need to bother, for getting 8bit FAST PWM.
