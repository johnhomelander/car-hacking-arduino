# Car Hacking
This is a project that I and my team have just started working on. This b


#### Remote Keyless Entry (RKE) Systems
These systems use the mechanism of locking/unlocking a car using radio frequency (RF) signals that are sent from a remote key fob, rather than using a mechanical key to unlock a car.

The very first key fobs in the early 90s used a static code system.  
The fobs transmitted the same code every time the button was pressed, and all the car had to do was listen for that static code and when it received it, unlock the car doors.  
This system is insecure, as all an attacker would have to do is sniff the code while the owner is unlocking/locking their car without them knowing, then replay it back to the car whenever they want to get in.

To combat this problem, rolling codes started to be used, wherein with every key press a unique code is sent from the key fob to the car using a pseudorandom number generator(PRNG). This code is then encrypted by the key fob using a special key ,only known to the key and the receiver in the car, before sending it to the car. The receiver in the car then decrypts the code
