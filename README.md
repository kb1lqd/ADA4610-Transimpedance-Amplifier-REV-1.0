Notes

2022-08-23

* Soldered the board together
* It works! But I did find some minor errors.
* The voltage output varies as expected with light over a wide range

Errors
* D1 footprint pin 1 assingment is backwards, this resulted in the diode being backwards
* The resulting current from the device is quite large resulting in the second amplifier stage being saturate in a lit room, I removed R7 to create a voltage follower and this alleviate the issues for now
* Placing the output on a scope it's clear there is a HF oscillation at 2.24mHz
** NOTE that the oscillation appears to be only on the 2nd stage output and not the first stage. Note that the second stage is now a voltage follower

2022-08-24

* Placed a 33pF capacitor across R8 and this stopped the oscillation
* I repopulated R7 with a 1K resistor
* There is some very very high frequency noise but pretty negligable it seems
* It works! I can definetley see an IRDA remote control signal at ~37KHz carrier
* It seems like if I want to use this in a bright room I'm going to have to turn the gains down
** Which is better - the TIA or the second stage?


To-Do
* [DONE] Track down oscillation
* [DONE] Detect light pulses in the scope and observe the results
* Detemirne rough frequency response - even if simulated with updated values (37KHz carrier pulses looked pretty rounded) - This may inform a reduction in capacitances or resistances)


