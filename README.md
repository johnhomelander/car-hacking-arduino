# Car Hacking
This is a project that I and my team have just started working on. This b


#### Remote Keyless Entry (RKE) Systems
These systems use the mechanism of locking/unlocking a car using radio frequency (RF) signals that are sent from a remote key fob, rather than using a mechanical key to unlock a car.

The very first key fobs in the early 90s used a static code system.  
The fobs transmitted the same code every time the button was pressed, and all the car had to do was listen for that static code and when it received it, unlock the car doors.  
This system is insecure, as all an attacker would have to do is sniff the code while the owner is unlocking/locking their car without them knowing, then replay it back to the car whenever they want to get in.

To combat this problem, rolling codes started to be used, wherein with every key press a unique code is sent from the key fob to the car using a pseudorandom number generator(PRNG). This code is then encrypted by the key fob using a special key ,only known to the key and the receiver in the car, before sending it to the car. The receiver in the car then decrypts the code and verifies the decrypted code and follows the command in the code. The receiver and key fob also use a counter for the number of codes(_i_ for reference here) used successfully the last time the car was unlocked.
This counter number is checked by the receiver to be between i+1 and i+n(where n is between 16 and 256) to account for the accidental key presses by the owner. This can also be an attack vector
The operating frequency for key fobs in US and Japan is 315 MHz and for Europe and other Asian countries is 433.92 MHz.

#### Using Arduino to carry out a car replay attack

* So basically, in this process, we would be using a transceiver with Arduino to listen for the signal in a particular frequency range from the key fob.
* Then we would be replaying this signal using the transceiver to the car to unlock/lock it.

This method can also be used for cars using the rolling codes
* We could press the unlock button on the key fob outside the range of the car so that it is not detected by the car(A bit of social engineering might be required for this). We can listen and catch this signal using our transceiver with Arduino.
* Then we can replay the signal to the car by getting in its range to unlock it. The car would unlock in this case as the code sent by us over the RF signal is new and has not been used before.


Reference Projects - 
* [Transmitting and Receiving data using Arduino and an RF module](https://www.electronicshub.org/arduino-rf-transmitter-receiver-module/)
* 
