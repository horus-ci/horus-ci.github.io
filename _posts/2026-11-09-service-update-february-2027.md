---
layout: post
title: "OSiRIS and HORUS continue, best effort, through February 2027"
date: 2026-11-09
author: "Shawn McKee for the OSiRIS and HORUS projects"
categories: [news]
tags: [news, osiris, horus, service-status]
---
{% include JB/setup %}

OSiRIS storage and HORUS computing did not end on 31 August 2026 as we announced last year. Both services are running and will continue on a **best-effort basis through February 2027**.

<!--excerpt-->

**What best effort means**

- The services stay up and we keep maintaining them, but there is no guaranteed availability or response time.
- Support continues by email: horus-help@umich.edu.
- Keep your own copy of any data you can't afford to lose.

**Looking beyond February 2027**

We may move the University of Michigan hardware to another location during February 2027, so that best-effort service can continue after that. We will post the details here, including any downtime, as soon as they are confirmed.

If your work depends on OSiRIS or HORUS after February 2027, please tell us at horus-help@umich.edu. Knowing who relies on the services helps us plan.

**Recent maintenance**

This autumn we upgraded or rebuilt most of the infrastructure. The OSiRIS Ceph storage cluster now runs Ceph Tentacle (20.2.4), nearly all servers run AlmaLinux 9.8, and the directory (LDAP), logging and monitoring services were rebuilt. The Puppet 8 upgrade we mentioned in December is under way: we are moving our configuration management from Puppet 7 to the newest OpenVox release from Vox Pupuli, the community-maintained continuation of Puppet.

This post replaces the 31 August 2026 end date in our [September 2025 notice]({% post_url 2025-09-11-horus-osiris-service-end %}). Updates for both services will be posted here on horus-ci.org.

Thank you,
Shawn McKee for the OSiRIS and HORUS projects
