---
weight: 2
title: "IPv6 Hell"
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


tags: ["IPv6"]
categories: ["projects"]

toc:
  auto: false
math:
  enable: true


images:
  - '/posts/making-a-label-printer-work-under-linux-using-agentic-ai/531647410-a39b1aa5-5e17-4656-906e-e92134ea1e62.jpg'


---

<!--more-->

## Introduction

I have been wanting to switch to IPv6 in my home network for a long time but until now I didn't dare to do it. Alhtough I had an understanding of IPv6 a big hurdle is unlearning what I have learned about IPv4 and all the habits I have developed over the years. For example plugging in a esp32 and looking up it's ip in the DHCP server.

## Comming from IPv4

One thing I hear a lot if just forget everything you know about IPv4 and start fresh. However that is not so easy.

Coming from IPv4 you may have learned to habits as well which bring up the following questions:

- How can I remember such long addresses? Short Answer: You don't.

- 



## Question


- How do devices get a fixed address if I don't have a DHCP server?

- How do devices get a DNS server address if I don't have a DHCP server?

- How can someone access my server from the outside?

- How can someone on IPv4 access my IPv6 server?

- How can I find a device on my network? Like when I connect a raspberry pi?

- How do IPv4 only devices connect to the internet?

- How can I access IPv4 only devices from a IPv6 device on the network?


OS Vendor	DNS Configuration Method	Why
Google (Android)	RDNSS only (in Router Advertisements)	Refuses to implement DHCPv6 entirely
Microsoft (Windows)	DHCPv6 only	Refused to implement RDNSS for years
Apple (macOS/iOS)	Both (RDNSS preferred)	Took the pragmatic middle path

Protocol	Purpose	Who Needs It
SLAAC	Address assignment	All clients get their IP this way (Android requires it)
RDNSS	DNS server distribution	Android, modern Windows, Apple devices
DHCPv6 (stateless)	DNS + other config	Legacy Windows, enterprise features
mDNS	Service discovery (.local)	Printers, Chromecast, cross-VLAN discovery

Your Need	Minimum Required
Android devices get IPv6 + DNS	SLAAC + RDNSS only
Windows clients get IPv6 + DNS	SLAAC + DHCPv6 stateless
Servers with stable addresses	DHCPv6 stateful (with static mappings) OR static config
Find printers across VLANs	mDNS repeater



SLAAC + RDNSS + mDNS


NAT64