
# Control4 driver for controlling Samsung TV via EX-LINK serial protocol

Tested with 55" Samsung Frame TV 2023 only.

I have switched to EX-LINK driver from the official IP driver to get more reliable and quicker input selection during TV startup.
It takes 20-30 seconds for my TV to startup and switch to the needed input using IP driver and even then it does not work every time, so manual input selection is needed.

Driver uses the following EX-LINK codes from the official Samsung documentation:


```
Power On	08 22 00 00 00 02 D4
Power Off	08 22 00 00 00 01 D5
Volume Up	08 22 01 00 01 00 D4
Volume Down	08 22 01 00 02 00 D3
Mute Toggle	08 22 02 00 00 00 D4
Info		08 22 0D 00 00 1F AA
Menu		08 22 0D 00 00 1A AF
Up		08 22 0D 00 00 60 69
Down		08 22 0D 00 00 61 68
Right		08 22 0D 00 00 62 67
Left		08 22 0D 00 00 65 64
Select		08 22 0D 00 00 68 61
Prev		08 22 0D 00 00 58 71
Back		08 22 0D 00 00 2D 9C
HDMI 1		08 22 0a 00 05 00 c7
HDMI 2		08 22 0a 00 05 01 c6
HDMI 3		08 22 0a 00 05 02 c5
HDMI 4		08 22 0a 00 05 03 c4
```

The delay between power and input selection command is set to 7 seconds, you may want to change that. 
I"ve found that 3 seconds delay works in most cases but up to 7 seconds delay is needed sometimes.
