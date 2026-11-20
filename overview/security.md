---
layout: default
title : Security
group: navigation
order: 1
group: overview
subnavgroup: overview
---
{% include JB/setup %}

HORUS follows best practice recommendations from the NSF-funded Center for Trustworthy Scientific Cyberinfrastructure (CTSC), while building on tools already secured and implemented for the previous OSiRIS project.

For user authentication, authorization, and organization, HORUS uses the InCommon framework and COmanage. Users log in with their institutional credentials; HORUS is not involved in creating their institutional accounts and does not store their passwords.

Monitoring tools (OpenSearch central logging, CheckMK, Prometheus) and auditing tools available within our AlmaLinux9 operating system help to identify security-related issues. HORUS also uses the ongoing institutional vulnerability scanning already in place for OSiRIS systems, extended to include the HORUS systems.

Operating system updates, including security fixes, are applied in regular patch rounds, and sooner for critical security fixes.
