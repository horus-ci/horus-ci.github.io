---
layout: post
category : article 
title: OSiRIS Updates for HORUS
tags : [ ]
---
{% include JB/setup %}

As the basis for the HORUS storage infrastructure, we rely upon OSiRIS for a reliable, resilient platform providing large-scale high performance storage.  OSiRIS currently provides over 1400 disks and 12 PB of raw storage space.   However, OSiRIS was originally deployed on a base operating system of CentOS 7 which is reaching End-of-Life (EOL) in June 2024.   Also, some of the tools, libraries and components were in need up upgrades to address security and functionality issues.  One of our main upgrades beyond the operating system, was PHP, which needed to be brought up to version 8.2.   Many of the upgrades introduced compatibilty issues and we need to work closely with various software providers to maintain functionality, while fixing security issues.  This work has taken most of the HORUS team's effort since the equipment was deployed and also required "best effort" help from the remaining OSiRIS team members.  

However we are happy to report success by the end of July and the team is now focused enabling a smooth onboarding process for our early adopters.


<!--excerpt-->

The OSiRIS platform underlying HORUS, was in need of significant updates for security and maintainability, and this work was completed by the end of July 2023.
