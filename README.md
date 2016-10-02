![Photo of RPi Speaker](https://github.com/zodoczi/RPi_Speaker/blob/master/rpi_speaker_2.jpg)
![Photo of RPi Speaker](https://github.com/zodoczi/RPi_Speaker/blob/master/rpi_speaker_1.jpg)

Integrated active amplifier PCB for Rapsberry Pi (versions 1,2 and 3). On board LM386 amplifier do the amplification of the weak PWM audio signal coming out of RPi GPIO.
Also an on board low pass filter helps reconsturging the analog audio signal from PWM. 

Amplifier board built, find test video on Youtube here: http://bit.ly/rpi_speaker

------------
Installation
------------

Latest Raspbian OS has Pigpio software pre-installed, this handles GPIO alternative function. 
So just strart it and configure GPIO18 into ALT5 mode in RPi 2 and 3 (routing audio PWM signal to amplifier PCB):
In RPi 1 PWM audio can acces at GPIO12 port, see schematic.

Commands:

```
sudo pigpiod # start daemon
pigs m 18 5 # set GPIO18 to mode ALT5, RPi 2 and RPi 3 
```

Playing music with for example omxplayer (included in Raspbian) take care to route audio signal to PWM port and not HDMI output (-o local switch below).
You can listen internet stream or offline audio files. This example starts a music station:

```
omxplayer -o local http://bbcmedia.ic.llnwd.net/stream/bbcmedia_6music_mf_p
```


-----------------------
Alternative GPIO config
-----------------------

If Pigpio doesn't work for you, try this method:

https://www.raspberrypi.org/forums/viewtopic.php?f=44&t=39138