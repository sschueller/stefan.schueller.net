---
weight: 2
title: "Rewiring a label printer"
date: 2026-04-05T18:30:16+02:00
lastmod: 2026-04-05T18:30:16+02:00
author: "Stefan Schüller"
authorLink: "https://github.com/sschueller/"
description: ""
draft: true
enableEmoji: true

featuredImage: "mini-labels"
resources:
  - name: label-printer-UI
    src: 2026-01-18-185249_668x826_scrot.png


tags: ["Agentic AI", "AI", "Kilocode", "Label Printer"]
categories: ["projects"]

toc:
  auto: false
math:
  enable: true


images:
  - '/posts/making-a-label-printer-work-under-linux-using-agentic-ai/531647410-a39b1aa5-5e17-4656-906e-e92134ea1e62.jpg'


---

<!--more-->

## Intruduction

In my [prevous post](/posts/making-a-label-printer-work-under-linux-using-agentic-ai/) about this printer I created alternate firmware to control the printer via PC and web using bluetooth. 

After I got all this working I was wondering if I could actually replace the bluetooth module and run a web server on the printer itself. Hence I went down another rabbit hole.

## The Goal

My next goal was to completly replace the BLE Module I found inside the printer with a custom one running an ESP-32S3 which I could flash. To do this I would need to figure out how the module communicates with the printer and how to interface with it.

Luckily the BLE module in the printer has a clearly marked PCB and even the model number of the BLE module. A common off the shelf BLE module used in many label printers.


## Protocol Sniffing

After some digging I found some documentation on the protocol used by the module and I could get some back and fourth from the printer with my customer ESP32S3. However the printer would stop responsing and I was missing something in my code.

I decided it would be easier to sniff the protocol between the module and the printer than trying to figure out what I needed to send. 

To do this I connected the printer and module to a Raspberry Pi and had an Agentic AI agent sniff the protocol between the two.


## Custom PCB




## Adding a display

## Hacking it all together
