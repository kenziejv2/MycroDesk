---
title: "MycroDesk"
github: "https://github.com/kenziejv2/MycroDesk"
description: "A custom macro pad featuring an ESP32-S3-WROOM-1 that acts like a native USB-HID controller. Includes a reversible 16-pin USB-C interface, AMS1117-3.3 power regulation, and modular peripheral support. I'm building this because it's pretty cool ngl. \n\nIt's also planned to have an OLED display for a built-in timer, paired with a rotary knob that lets you set the countdown and control your desktop's master volume (+media playback!)."
created_at: "2026-11-21"
total_time: "5h 48m"
---

# November 21, 2026: Completed the core schematics & power architechture

Today, I completed the core schematics on KiCad for my project. This is my first time doing like this, but **what I did was:**
1. Configured the core ESP32-S3-WROOM-1 module layout alongside with reset (EN) and boot (GPIO 0) control circuits.
2. Add the AMS1117-3.3 power regulation stage to reduce the 5V VBUS with appropriate input and output filtering capacitors.
3. Set up the USB-C data interface and ground net consolidation.

Also, I'm learning KiCad while progressing (with some help from my dad) :D

It did **good!** I even re-checked the hardware guidelines with my connections so that I won't get any bugs or errors that could've been fatal (I hope...).

![](https://fabricate.hackclub-assets.com/8fd4aa5decf63f19c30808b0d56719753581c491c171a2c89cbdd15b146644d1/image-png/Screenshot%202026-11-21%20231103.png)

**Total time spent: 3h 18m**

# November 22, 2026: Completed & verified the MycroDesk schematics

Today, I just found out about ERC and tested it. I got like **26 ERRORS** and **4 WARNINGS.** 
So, I took some time to fix it and also continuing my project.

**What I did was:**
1. Fix those bad errors and warnings. I placed No Connect Flags into each unused pins and Power Flag for power nets where input weren't actively "connected"
2. Added Rotary Encoder (EC11) and connected Phase A to GPIO17, B to GPIO18, and Common to GND. I also add No Connect Flags to each unused S1 and S2.
3. Added the 4-pin SSD1306 I2C OLED display connector (J2) and route each pins (1 -> GND, 2 -> 3.3V, 3 -> `I2C_SCL` -> GPIO1, 4 -> `I2C_SDA` -> GPIO2)

Then, I tested the ERC and **no signs of errors or warnings!** Now, I can declare that it did good this time :)

![](https://fabricate.hackclub-assets.com/4193a6ecfc791fd066d854d37089c6d63f25afa58fa589dd2ae21b6d3e1105f1/image-png/Screenshot%202026-11-22%20095400.png)

**Total time spent: 2h 30m**
