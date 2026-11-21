---
layout: post
title: "HORUS and the OSPool: November 2026"
date: 2026-11-19
author: "Shawn McKee for the OSiRIS and HORUS projects"
categories: [news]
tags: [news, horus, osg]
---
{% include JB/setup %}

HORUS gives its otherwise idle cores to the OSG's Open Science Pool (OSPool), which runs research jobs from across the country. In November 2026 more than a thousand OSPool jobs typically run on HORUS at once, about half of them on the `lg` nodes.

<!--excerpt-->

**How it works**

The OSG submits pilot jobs to HORUS's Slurm. Each pilot takes one core and runs OSPool work until it ends; HORUS users' own jobs get higher priority through fair-share. HORUS joined the OSPool in January 2024 ([OSG engagement]({{ site.baseurl }}documentation/osgengage.html)).

**A bug found and fixed together with the OSG**

On 16 November one OSPool user's jobs each wrote 30 to 40 GB, far more than the disk they had asked for. It filled the local disks of several `lg` nodes, which then stopped taking new work. Looking into it, we found that a rule in the OSG pilot configuration meant to stop such jobs never took effect, because one condition in it was inverted. The OSG team confirmed the bug the same day and applied a temporary fix to their pilot configurations the next day. By 18 November nearly 80% of the pilots on HORUS were already running with it, and a permanent fix is on its way in an upcoming HTCondor release.

Thank you to Tim Cartwright and the OSG team for their quick work.

Shawn McKee for the OSiRIS and HORUS projects
