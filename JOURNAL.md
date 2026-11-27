---
title: "MycroDesk"
github: "https://github.com/kenziejv2/MycroDesk"
description: "A custom macro pad featuring an ESP32-S3-WROOM-1 that acts like a native USB-HID controller. Includes a reversible 16-pin USB-C interface, AMS1117-3.3 power regulation, and modular peripheral support. I'm building this because it's pretty cool ngl. \n\nIt's also planned to have an OLED display for a built-in timer, paired with a rotary knob that lets you set the countdown and control your desktop's master volume (+media playback!)."
created_at: "2026-11-21"
total_time: "14h 6m"
---

# November 21, 2026: Completed the core schematics & power architechture
<!-- fabricate:entry 3589 -->

Today, I completed the core schematics on KiCad for my project. This is my first time doing like this, but **what I did was:**
1. Configured the core ESP32-S3-WROOM-1 module layout alongside with reset (EN) and boot (GPIO 0) control circuits.
2. Add the AMS1117-3.3 power regulation stage to reduce the 5V VBUS with appropriate input and output filtering capacitors.
3. Set up the USB-C data interface and ground net consolidation.

Also, I'm learning KiCad while progressing (with some help from my dad) :D

It did **good!** I even re-checked the hardware guidelines with my connections so that I won't get any bugs or errors that could've been fatal (I hope...).

![](https://fabricate.hackclub-assets.com/8fd4aa5decf63f19c30808b0d56719753581c491c171a2c89cbdd15b146644d1/image-png/Screenshot%202026-11-21%20231103.png)

**Total time spent: 3h 18m**

# November 22, 2026: Completed & verified the MycroDesk schematics
<!-- fabricate:entry 3676 -->

Today, I just found out about ERC and tested it. I got like **26 ERRORS** and **4 WARNINGS.** 
So, I took some time to fix it and also continuing my project.

**What I did was:**
1. Fix those bad errors and warnings. I placed No Connect Flags into each unused pins and Power Flag for power nets where input weren't actively "connected"
2. Added Rotary Encoder (EC11) and connected Phase A to GPIO17, B to GPIO18, and Common to GND. I also add No Connect Flags to each unused S1 and S2.
3. Added the 4-pin SSD1306 I2C OLED display connector (J2) and route each pins (1 -> GND, 2 -> 3.3V, 3 -> `I2C_SCL` -> GPIO1, 4 -> `I2C_SDA` -> GPIO2)

Then, I tested the ERC and **no signs of errors or warnings!** Now, I can declare that it did good this time :)

![](https://fabricate.hackclub-assets.com/4193a6ecfc791fd066d854d37089c6d63f25afa58fa589dd2ae21b6d3e1105f1/image-png/Screenshot%202026-11-22%20095400.png)

**Total time spent: 2h 30m**

# November 24, 2026: Tried to make a PCB
<!-- fabricate:entry 3834 -->

Soo... For the past few days, I've been working on my PCB. Here's a progress! 
I've learned how to design a custom PCB from tutorials and tried it myself. It's hard but worth it :D

Basically, I've learned about placing components and copper traces :)

Stay tuned for the next progress!

![](https://fabricate.hackclub-assets.com/e0e99643bc39d7d1144a0d7d079a7c0e3639d62e6a57c59cb17a61bcc49a8cdc/image-png/Screenshot%202026-11-24%20190948.png)
![](https://fabricate.hackclub-assets.com/1daf03292327b3db2fe25ac4e6afc2686e22f3c079a211c4414db509ebb16d02/image-png/Screenshot%202026-11-24%20191739.png)

**Total time spent: 2h 24m**

# November 25, 2026: Routed the 6 main keys
<!-- fabricate:entry 3890 -->

I did some trace jumping because of how dense the wires. Overall? It's awesome!
Sometimes, I ended up trying to re-design the routing lol :P

But, it's looking great! I know some of you maybe aren't satisfied about my wiring, I'll try to fix it!

![](https://fabricate.hackclub-assets.com/6fe66be5e8a85174e06b8b6156a09b37f389b21b76c7bf8b89fa3d700cf2e92a/image-png/Screenshot%202026-11-25%20201749.png)
![](https://fabricate.hackclub-assets.com/8bb18d3118e22bff7a682a980e95845064a69462ad8c823d43a408cb4499f025/image-png/Screenshot%202026-11-25%20201957.png)

**Total time spent: 1h 18m**

# November 26, 2026: Completed Routing the PCB
<!-- fabricate:entry 3947 -->

**FINALLY, I DID IT!**
I've routed my PCB :D

I've routed the Rotary Encoder and the evil switch >:)
Afterwards, I've used Copper Ground on both F.Cu and B.Cu layers and did some via stitching to keep it stable! I got 0 errors and warnings when I did DRC! 

This is fun ngl :))

![](https://fabricate.hackclub-assets.com/1bd2cdc24819c25dc8b154d17251fbb0a97bbcb1a48c4d0614ab2532936ae0ce/image-png/Screenshot%202026-11-26%20180557.png)
![](https://fabricate.hackclub-assets.com/d2bd13f953585fdc9d0f524a3d7e6709c5a9e461afc3ea08c40d00a170b916ef/image-png/Screenshot%202026-11-26%20180643.png)
![](https://fabricate.hackclub-assets.com/d51918e441833ded1c130398d28b9c650547e1287aab7b01f9d2037652477625/image-jpeg/WhatsApp%20Image%202026-11-26%20at%2018.08.11.jpeg)
![](https://fabricate.hackclub-assets.com/ec0139e94053e1920d42dc62220ad70438621268afb288310c034641c5ae613a/image-jpeg/WhatsApp%20Image%202026-11-26%20at%2018.09.14.jpeg)
![](https://fabricate.hackclub-assets.com/bd88cb8893e4a501908701add8fbcccfb8ee0cca87696d013c26f85d2ee829eb/image-jpeg/WhatsApp%20Image%202026-11-26%20at%2018.09.34.jpeg)

**Total time spent: 3h 12m**

# November 28, 2026: Designed a rough shape for the case in Onshape
<!-- fabricate:entry 4074 -->

I've designed a rough shape for the case today. I used my PCB 3D model for a reference so I could get the dimension right. 

**LENGTH: 150 mm**
**WIDTH: 88 mm**
**HEIGHT: 20 mm**

I'm using Onshape for making this, still learning though.

![](https://fabricate.hackclub-assets.com/3537868a06060e53dad255ff4937b84ff28e7d70bf6261333cb95926707a2433/image-png/Screenshot%202026-11-28%20064024.png)
![](https://fabricate.hackclub-assets.com/4a7e5c1915ebd4f56af9f52bb84e078c7e23fc3a246e5d6491262974631c7a9b/image-png/Screenshot%202026-11-28%20064053.png)
![](https://fabricate.hackclub-assets.com/48988f43075b1833d1a2b5d1efa8bb68fb21616f818632e9f9c2356d2eeeb123/image-png/Screenshot%202026-11-28%20064128.png)
![](https://fabricate.hackclub-assets.com/79811c1de776db65a6b5251d501b42e67ddb82d7e91f24821f60bac04ff3467d/image-png/Screenshot%202026-11-28%20064144.png)

**Total time spent: 1h 24m**
