# Splunk SSH Brute-Force Detection and Incident Investigation

 **Project Type:** Detection Engineering • Incident Response • SIEM • Linux Security

This project demonstrates the end-to-end detection and investigation of a simulated SSH brute-force attack against an Ubuntu server. Linux authentication logs were centralized in Splunk using the Splunk Universal Forwarder, custom SPL detections were developed, the attack was investigated through a SOC-style workflow, and automated containment was verified using Fail2Ban and nftables.

## Overview

This project extends a Linux SSH brute-force lab into a centralized SIEM detection and incident-investigation workflow.

An Ubuntu server hosted on a BMAX B1 Pro mini PC generated Linux authentication logs. The logs were forwarded to Splunk Enterprise running on a PowerSpec workstation using the Splunk Universal Forwarder.

A controlled SSH brute-force simulation was performed with Hydra. Splunk Processing Language (SPL) searches were then used to detect the activity, identify the attacking source, determine the targeted account, assess whether authentication succeeded, visualize the attack timeline, and verify containment through Fail2Ban and nftables.

## Objectives

- Forward Ubuntu authentication logs into Splunk
- Build threshold-based SSH brute-force detection logic
- Extract source IP and targeted-user fields from raw logs
- Investigate the scope and timeline of the activity
- Determine whether the attack resulted in successful authentication
- Build a reusable SOC investigation dashboard
- Verify automated containment using Fail2Ban and nftables
- Document configuration and troubleshooting decisions

## Lab Architecture

```text
PowerSpec Workstation
├── Windows 11
├── Splunk Enterprise Free
├── Ubuntu WSL
└── Hydra
        |
        | SSH authentication attempts
        v
BMAX B1 Pro Mini PC
└── Ubuntu Server Virtual Machine
    ├── OpenSSH
    ├── /var/log/auth.log
    ├── Splunk Universal Forwarder
    ├── Fail2Ban
    └── nftables
        |
        | TCP 9997
        v
Splunk Enterprise
