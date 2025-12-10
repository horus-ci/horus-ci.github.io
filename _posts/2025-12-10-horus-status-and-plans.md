---
layout: post
category: article
title: HORUS Status and Plans — Infrastructure Updates and Future Services
date: 2025-12-10
author: HORUS Project Team
categories: [news]
tags: [HORUS, OSiRIS, Ceph, AlmaLinux, Puppet, LLM]
---
{% include JB/setup %}

The HORUS project team is currently working on a number of important renovations and upgrades to our hosts, services, and tools to better serve our research community.

**New LLM Assistant for Registered Users**

In approximately one month, we will be launching a new Large Language Model (LLM) tool specifically focused on HORUS and OSiRIS. This assistant will be available to all registered users and is designed to help with common questions about how to use our resources, debug issues, and optimize your workflows. The LLM will provide quick first-response guidance; while we hope it will be accurate and helpful, please remember it is intended to complement—not replace—our support staff. For complex issues or when you need personalized assistance, our team at horus-help@umich.edu remains your best resource.

**AlmaLinux 9 Migration Continues**

We are actively upgrading our remaining infrastructure hosts to AlmaLinux 9, continuing our effort to maintain a modern, secure, and well-supported operating system foundation. This migration includes critical services such as our perfSONAR monitoring systems, the Wiki, the LDAP authentication server, the ELK (Elasticsearch, Logstash, Kibana) logging and analytics system, and the COmanage identity management platform. These upgrades will improve security, performance, and long-term maintainability.

**Puppet Infrastructure Upgrade**

In the slightly longer timeframe, we are planning to upgrade our configuration management system from Puppet 7.34 to Puppet 8.7 or later. This upgrade will provide us with enhanced features, improved performance, and continued vendor support for managing our infrastructure at scale.

**OSiRIS Ceph Storage Maintenance**

We continue to maintain and update the OSiRIS Ceph deployment that provides the storage foundation for HORUS. Currently, the system has just under 12 petabytes of raw storage capacity and requires ongoing attention to ensure reliability and performance for all users.

**Looking Ahead**

All of these infrastructure improvements are intended to help enable a possible future extension of HORUS and OSiRIS services for users beyond August 2026. However, we want to be clear that our current operational plans still have services shutting down on August 31, 2026, as previously announced. These upgrades position us well should additional funding or institutional support become available to extend the project timeline.

We appreciate your continued use of HORUS and OSiRIS. If you have questions or concerns about any of these updates, please don't hesitate to contact us at horus-help@umich.edu.

<!--excerpt-->

HORUS infrastructure updates: New LLM assistant for users coming in ~1 month; AlmaLinux 9 migration in progress (perfSONARs, Wiki, LDAP, ELK, COmanage); Puppet upgrade to 8.7+ planned; ongoing Ceph maintenance (~12 PB storage). Work aims to enable possible service extension beyond August 2026, though current plans remain unchanged.
