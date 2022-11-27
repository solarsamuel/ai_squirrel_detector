# ai_squirrel_detector
Build a squirrel detector using a Raspberry Pi 4 and Adafruit Braincraft Hat

Video instructions are here: https://www.youtube.com/watch?v=FXdtcuyrMAc

1. Buy a Raspberry Pi 4 and Adafruit Braincraft hat then follow this tutorial
https://learn.adafruit.com/running-tensorflow-lite-on-the-raspberry-pi-4?view=all

It's easiest to use Putty to SSH into the Raspberry Pi and copy the Adafruit instructions line by line.

2. Install the gpiozero python module in the Raspberry Pi virtual environment
3. Open the pitft_labeled_output.py file using nano editor on the Raspberry Pi
4. Add the following code toward the top of pitft_labeled_output.py

#ADDED FOR SQUIRREL DETECTOR ==============
from gpiozero import LED
from time import sleep
led = LED(21)
led.off()
#==========================================

5. Add the following for the squirrel detector after where is says "persistent_obj = True
  #ADDED FOR SQUIRREL DETECTOR ==============
                    if name == 'lynx':
                        led.on()
                        sleep(1)
                    elif name == 'Egyptian_cat':
                        led.on()
                        sleep(1)
                    elif name == 'fox_squirrel':
                        led.on()
                        sleep(1)
                    elif name == 'marmoset':
                        led.on()
                        sleep(1)
                    else:
                        led.off()
     #===========================================

6. Wire in a LED with 800 ohm resistor in series between the desired GPIO pin and ground. In this case GPIO 21. 
7. Run the program and test it with printed images. The LED should light up when it sees the lynx, Egyptian_cat, marmoset, and fox_squirrel classifiers.
