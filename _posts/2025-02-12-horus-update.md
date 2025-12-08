---
layout: post
category: article
title: HORUS / OSiRIS update — new lg nodes, Ceph upgrade, and service reminder
date: 2025-02-12
tags: [news, infrastructure, slurm, ceph, osiris]
---
{% include JB/setup %}

HORUS and OSiRIS updates (2025-02-12): 7 new large-memory CPU nodes added to the HORUS SLURM cluster and the OSiRIS Ceph cluster has been upgraded.

<!--excerpt-->

Key updates

- HORUS: We added 7 new large-memory, large-CPU nodes to the HORUS SLURM cluster in a new partition named "lg". Each node provides 1.5 TB of RAM, 384 logical CPUs, and dual 100 Gbps network interfaces.

- OSiRIS: We upgraded the OSiRIS Ceph release from 18.2.4 to 19.2.1.

Service reminder

The infrastructure is being operated on a best-effort basis until August 2026. If you have substantial data stored in OSiRIS, please begin planning where it will reside after August 2026 and consider deleting data you no longer need.

Contact

Questions or concerns: horus-help 'at' umich.edu

Thanks,

Shawn McKee for the HORUS and OSiRIS projects
