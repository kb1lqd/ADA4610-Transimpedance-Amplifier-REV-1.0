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


To-Do
* Track down oscillation
* Detect light pulses in the scope and observe the results