---
title: "MycroDesk"
github: "https://github.com/kenziejv2/MycroDesk"
description: "A custom macro pad featuring an ESP32-S3-WROOM-1 that acts like a native USB-HID controller. Includes a reversible 16-pin USB-C interface, AMS1117-3.3 power regulation, and modular peripheral support. I'm building this because it's pretty cool ngl."
created_at: "2026-11-21"
total_time: "3h 18m"
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
