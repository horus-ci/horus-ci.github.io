---
layout: default
title : Project Timeline
group: navigation
order: 2
group: overview
subnavgroup: overview
---
{% include JB/setup %}

The project has two primary phases. The first year is devoted to developing, tuning, and integrating the initial hardware and software components at our sites, while focusing on onboarding early-adopter science domains. The second year we plan to complete the hardware installation (with updates to configurations and type of resources based on the first year) and open the infrastructure to the rest of our planned users and new researchers found via our outreach.   The set of milestones/activities and their status are shown below.

| Symbol | Meaning  |
| ------ | -------- |
| ✔️  | Completed task |
| 🔶  | Task underway but not complete |
| ❗  | Task delayed, typically because of dependency not being ready |

### Startup — First Two Months
- ✔️ Hold a kick-off meeting with research stakeholders to formalize HORUS plans including interface software development, outreach and hardware plans
- ✔️ Create HORUS GitHub project
- ✔️ Place orders for Year 1 equipment
- ✔️ Set up Mattermost, mailing lists

### Months 3-6 — Initial Deployment
- ✔️ Deploy hardware (delayed till May 2023)
- ✔️ Identify science domains for onboarding
  - ✔️ Mathematics of Turbulent 3D Flows / Kyle Schwiebert / Michigan Tech University
  - ✔️ Network Telescope / Michael Kallitsis / Merit
  - ✔️ Quantum Chemistry / Alexander Rusakov / Oakland University
- 🔶 Prototype and deploy user-facing components identified in kick-off (_partially complete_)
- ✔️ Deploy perfSONAR instances in Merit
- 🔶 Install initial HTCondor and connect to OSG/PATh hosted CE (_HTCondor deployed; no PATh connection yet_)
- ✔️ Conduct first HORUS webinar (_December 22, 2022_)

### Months 7-12 — Tuning and Evaluation
- ✔️ Engage with early adopters about their access, ease-of-use, and workloads
- ❗Tune and test dynamic configurations exposing slices of computational hosts (_delayed_)
- 🔶 Verify access/authorization mechanisms and associated accounting and auditing (_partially complete_)
- ❗Gather, summarize, publish metrics (_delayed_)
- ❗Conduct second HORUS webinar (_awaiting early adopter feedback_)
- 🔶 Submit first code release on GitHub (_updates from upgrades and security fixes in place_)
- Submit end-of-year evaluation report

### Months 13-15 — Prepare for Year 2
- Review early adopters feedback
- Evaluate hardware configurations based on Year 1 and plan updates
- Order remaining hardware
- Update HORUS documentation/code
- Conduct third HORUS Webinar
- Review data management plan (DMP) status and undertake any required actions

### Months 16-18 — Onboarding
- Engage with remaining science domains and plan their onboarding
- Revise and update documentation
- Evaluate user support and issues
- Deploy remaining hardware
- Update HORUS documentation/code

### Months 18-21 — Evaluation/Evolution
- Conduct internal review of user access, monitoring, and management tools
- Survey all science domains for feedback
- Implement updates based on feedback
- Conduct fourth HORUS webinar
- Update HORUS documentation/code

### Months 22-24 — Project Transition, Wrap-Up
- Send out final survey and feedback request to science domains
- Publish HORUS results (dynamic resource allocation, tools and techniques)
- Finish DMP tasks
- Transition HORUS managed resources to institutional control
- Complete final evaluation and report
