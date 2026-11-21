---
layout: post
title: "HORUS jobs are now held to the memory they request"
date: 2026-11-19
author: "Shawn McKee for the OSiRIS and HORUS projects"
categories: [news]
tags: [news, horus, slurm]
---
{% include JB/setup %}

Since 18 November 2026, Slurm on HORUS holds every job to the memory it requests. If you don't ask for memory, your job gets the partition's default per CPU, which may be less than it needs.

<!--excerpt-->

**Why we made the change**

On 18 November, a few jobs that asked for 62.5 GB each used up to twice that. Three compute nodes ran out of memory, and the jobs of everyone else on those nodes were interrupted. With the new limit, a job that uses far more than it asked for is stopped on its own, and the node and the other jobs keep running.

**What to do**

- Ask for the memory your job needs: `#SBATCH --mem=8G` for the whole job on each node, or `#SBATCH --mem-per-cpu=4G`.
- Without either, the default per CPU is 2,000 MB in `lc` and `lm`, 3,000 MB in `lg` and 4,000 MB in `batch`.
- A job may use up to 10% more than it asked for. In that margin it is slowed down while memory is reclaimed. Beyond 10% it is stopped, with the state `OUT_OF_MEMORY`.
- To see what a finished job used: `sacct -j <jobid> -o JobID,ReqMem,MaxRSS,State`. Ask for somewhat more than the peak.

The [SLURM page]({{ site.baseurl }}documentation/slurm.html) lists the partitions, their memory defaults and their limits.

Questions, or a job that was stopped and you're not sure why: horus-help@umich.edu.

Thank you,
Shawn McKee for the OSiRIS and HORUS projects
