---
layout: post
title: "HORUS status and plans"
date: 2025-12-10
author: "HORUS Project Team"
categories: [news]
tags: [HORUS, OSiRIS, Ceph, AlmaLinux, Puppet, LLM]
---

The HORUS project team is undertaking a range of renovations and upgrades to hosts, services, and tooling to improve reliability, security, and performance for current users. Many of these changes are ongoing and are intended to reduce incidents and simplify operations in the coming months.

One exciting new capability we expect to make available to registered users in about one month is a dedicated LLM (large language model) focused on HORUS and OSiRIS. This tool will help users with questions about how to use resources, debug common problems, and optimise workflows. It is intended as a quick first-response aid to point users toward likely fixes and useful documentation — not as a replacement for our human support staff. For complex or unresolved issues, please continue to open support tickets so the team can follow up.

We are continuing the migration of the remaining hosts to AlmaLinux 9. Examples of systems being updated include our perfSONAR nodes, the project Wiki, the LDAP server, the ELK (Elasticsearch/Logstash/Kibana) system, and the CoManage deployment. These upgrades are focused on improving long-term supportability and security posture.

In the slightly longer timeframe we plan to upgrade Puppet from 7.34 to Puppet 8.7+; this upgrade will be coordinated and tested to avoid disruption to production services. We will share more details and maintenance windows as the upgrade schedule is finalized.

We also continue routine maintenance and updates of the OSiRIS Ceph storage deployment, which currently provides just under 12 petabytes of raw capacity. Ongoing work ensures the cluster remains healthy and performant for user workloads.

All of these efforts are intended to help enable a possible extension of HORUS and OSiRIS service availability beyond August 2026. At the same time, we need to be clear that the current plan still anticipates a shutdown of services on August 31, 2026. We will communicate any changes to those plans as they are confirmed.

If you have questions about these changes, need assistance, or would like early access to the LLM when it becomes available, please contact the HORUS support team or open a support ticket.
