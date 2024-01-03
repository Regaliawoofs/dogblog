---
title: "AWGG - RF Hacking Recommendations"
date: 2024-01-3T09:03:20-08:00
draft: false
---



**A Wolf Gal's "Getting Started" Guide to RF Hacking for Dummies:**

More and more people are wondering where I get my kit from, especially people wanting to break into infosec, so I'm putting this together to hopefully give some basic recommendations for intro wireless pentesting equipment. This is NOT a comprehensive list, nor is it the be-all-end-all of equipment either, but rather some tools I've used in my day-to-day doing wireless audits.

------------------------------------------

**HARDWARE:**

RTL-SDR - Receive only, but that's fine bc it's $20, and you can easily save the recordings to attack later with a transceiver. (Rx)

HackRF One - Bought on eBay for around $150, stupid cheap compared to MSRP. The most bang-for-your-buck option. (Rx/Tx)
- Mayhem Firmware - Extremely useful modded firmware for the platform that enables spoofing and a whole host of other tools.
- Portapak hardware is excellent for mobile use, and extremely recommended if you don't have the luxury of a static site to operate from.

(Opt.) Yardstick One - Typically found for ~$100, used for sub-GhZ stuff (doorbells, garage doors, and the like) (Rx/Tx)

A mid-to-high-range Alfa card that's dual-band will work wonders. AC1900 is on Amazon, with good specs. (Rx/Tx... Duh.)

Yagi Antennas - Available at many online retailers, amazon has them for a reasonable price, and some are directional. 

------------------------------------------

**SOFTWARE:**

Here's the laundry list to install for wireless/SIGINT ops:
Kismet - https://github.com/kismetwireless/kismet -- Recon, packet capture, basically a tool to grab everything and the kitchen sink
FISSURE - https://github.com/ainfosec/FISSURE -- Framework for RF pentesting.
URH - https://github.com/jopohl/urh -- All-in-one tool for RF auditing.
(Opt.) WiGle - For the occaisional wardriving outing

------------------------------------------

Using the Feds to our Advantage:

Typically, certain devices have ranges of frequency that they operate, and our gracious cuckold overlords in the states, known as the FCC, have their steel-toed boot on anything that does so much as a sneeze over the radio spectrum...Has a catalog of every device, and where it operates. You can use this to several advantages, such as IOT, where hardware hacking can also be utilized on these targets. The FCC takes photos of the board, letting anyone see the internals... which, if you come from the hardware hacking scene, is fucking huge for obvious reasons. (https://www.fcc.gov/oet/ea/fccid)

------------------------------------------

**DISCLAIMER: I am not responsible for anything you idiots do with this knowledge, you should do proper research on the laws governing your radio communications in your Country, State and/or Province. I am also not responsible for any damage to hardware done by incorrect usage of tools linked to in this Document. Should there be any questions regarding wireless penetration attacks, direct them to Google. Y'all are hackers, act like it.**

That being said, have fun!

-RW