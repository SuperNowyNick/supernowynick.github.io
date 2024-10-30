---
title: "Resetting Cisco 896VAG-LTE Router to factory settings with old IOS 15.5(3)M5 firmware"
date: 2024-10-30
---

---

💡 **Takeaway note: In order to reset old Cisco Router with old firmware I randomly pressed `reset` button at the back of it at startup to reset it to factory settings.**

---

So recently I bought a used Cisco 896VAG-LTE Router for a decent price. I've never used Cisco devices and wasn't sure if it will work at all.
After receiving it I've plugged in the power supply and realized that I need a special console cable that emulates RS232 in order to connect to the configuration console.
So once I got proper 'USB to RJ45 console cable' I was able to connect to it and verify that it indeed works.

---
Connection parameters:
 - Baud rate: 9600
 - Data bits: 8
 - Parity: none
 - Stop bits: 1
 - Flow control: XON/XOFF
---

Unfortunately, I wasn't able to change anything in configuration since it required logging in and I wasn't provided with the password by the seller.
Moreover, I could see the following terminal output which didn't increase my chances of getting grasp of it:
```
PASSWORD RECOVERY FUNCTIONALITY IS DISABLED
```

So after a short search I've found following procedure for resetting it to factory defaults (e.g. [here](https://community.cisco.com/t5/other-network-architecture-subjects/password-recovery-functionality-is-disabled/td-p/2973976)): **Use break sequence in terminal**.
I did try all the tips on the matter I could find, but none of the methods for triggering the break sequence and reset worked.
I couldn't find any other reset procedure for this device on the internet.

And when I lost all hope I resorted to brute **pressing of the reset button at the back of the router chassis**. Apparently doing it after power cycling the router resulted in a factory reset, because I could see following output in the terminal:

```
Would you like to enter the initial configuration dialog? [yes/no]:
```
And I could set everything up from the scratch.

So sometimes it's best to try least elegant but logical (and non-documented) methods to get something done.
