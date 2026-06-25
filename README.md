# Homelab SIEM and Security Scanner Orchestrator

An automated, zero-trust deployment engine designed to stand up a robust security monitoring infrastructure on local home networks. 

This project strips away hours of manual database, firewall, and configuration alignment, packaging the entire lifecycle into a clean Ubuntu PPA native asset.

## Project Intent
To deliver a streamlined, lightweight framework that provisions network isolation barriers, deploys essential threat-scanning dependencies, and bootstraps a production-ready Wazuh and ELK Stack ecosystem on a single node.

## What's Inside
* Zero-Trust Network Perimeter (UFW): Locks down host ingress traffic, permitting access only to secure management interfaces and essential SIEM collection pipelines.
* Core Monitoring Layer (Wazuh and ELK Engine): Standardizes the ingestion of host security telemetry and exposes a comprehensive dashboard for threat analytics.
* Integrated Scanner Suite: Pulls down and hooks standard diagnostic utilities into system log paths:
  * nmap: Network mapping and vulnerability profiling.
  * clamav: Local system endpoint malware detection.
  * jq and openssl: Structured data manipulation and cryptographic operations.

---

## Quick Deployment Guide

To deploy this project on any fresh Ubuntu 24.04 LTS (noble) node, run the following sequence in your terminal:

```bash
# 1. Register the PPA repository
sudo add-apt-repository ppa:rist138/ppa -y

# 2. Update local indexing pools
sudo apt update

# 3. Pull down the package and its recommended dependencies
sudo apt install -y homelab-siem-scanner

# 4. Initialize the interactive orchestration engine
homelab-siem-setup
```

Note: The core stack components require a minimum of 4GB of RAM to run reliably.

## License
Distributed under the open-source GPL-3 License. See debian/copyright for complete legal text mappings.
