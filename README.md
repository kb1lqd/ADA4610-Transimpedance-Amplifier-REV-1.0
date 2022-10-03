Notes

# 2022-08-23

* Soldered the board together
* It works! But I did find some minor errors.
* The voltage output varies as expected with light over a wide range

## Errors
* D1 footprint pin 1 assingment is backwards, this resulted in the diode being backwards
* The resulting current from the device is quite large resulting in the second amplifier stage being saturate in a lit room, I removed R7 to create a voltage follower and this alleviate the issues for now
* Placing the output on a scope it's clear there is a HF oscillation at 2.24mHz
** NOTE that the oscillation appears to be only on the 2nd stage output and not the first stage. Note that the second stage is now a voltage follower

# 2022-08-24

* Placed a 33pF capacitor across R8 and this stopped the oscillation
* I repopulated R7 with a 1K resistor
* There is some very very high frequency noise but pretty negligable it seems
* It works! I can definetley see an IRDA remote control signal at ~37KHz carrier
* It seems like if I want to use this in a bright room I'm going to have to turn the gains down
** Which is better - the TIA or the second stage?

# 2022-10-03

I've built up a bit of infrastructure around this TIA:
* Headphone amplifier to output the audio frequencies directly into headphones
* Listened to external light sources with a len assembly 3 miles away
* Built a simple audio light transmitter

I've noticed a faire bit of noise in the circuit. Hooking a scope up to the TP output I see a fairly complex oscillation between 30KHz and 97KHz. There is a different noise on the TIA output directly much smaller prior to the line driver amplifier.

**Noise on the TIA PCB 50 Ohm Output***

![](Photos\2022-10-03_TPOUTPUT_OSC_1.png)

** Noise on the TIA Output directly**

![](Photos\2022-10-03_TIA_OUTPUT_OSC_2.png)

I can see and hear the 120 Hz hum from my indoor (dim) lights that this noise is ontop of.

![](Photos\2022-10-03_TIA_OUTPUT_OSC_1.png)




# To-Do
* [DONE] Track down oscillation
* [DONE] Detect light pulses in the scope and observe the results
* Detemirne rough frequency response - even if simulated with updated values (37KHz carrier pulses looked pretty rounded) - This may inform a reduction in capacitances or resistances)
