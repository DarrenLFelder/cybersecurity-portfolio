# NIST CSF ICMP DoS Incident Analysis

## Project Overview

This project applies the National Institute of Standards and Technology Cybersecurity Framework (NIST CSF) to a simulated network security incident involving an ICMP flood Denial-of-Service (DoS) attack.

The objective was to analyze the incident using the five NIST CSF functions: Identify, Protect, Detect, Respond, and Recover.

## Incident Summary

A company's internal network became unavailable for approximately two hours after a malicious actor flooded the network with ICMP packets. An improperly configured firewall allowed the traffic to enter the network and overwhelm network resources.

The incident management team blocked incoming ICMP traffic, took non-critical services offline, and restored critical network services.

## NIST CSF Analysis

### Identify

The investigation identified an unconfigured firewall as a major vulnerability. The ICMP flood affected the internal network and prevented legitimate users from accessing network services and resources.

### Protect

Firewall ICMP rate limiting was implemented to control excessive incoming ICMP traffic. An IDS/IPS was also implemented to detect and filter ICMP traffic exhibiting suspicious characteristics.

### Detect

Source IP address verification was configured to help identify spoofed IP addresses. Network monitoring software was implemented to continuously monitor traffic and identify abnormal patterns that could indicate another attack.

### Respond

The incident management team blocked incoming ICMP traffic and took non-critical network services offline to contain the attack. Network logs and traffic data can be analyzed during future incidents to determine the source and characteristics of suspicious activity.

### Recover

Critical network services should be restored first and verified for normal and secure operation. Once the network is stable and the threat has been contained, non-critical services can safely be returned to operation.

## Skills Demonstrated

- NIST Cybersecurity Framework (CSF)
- Incident response
- Network security
- ICMP traffic analysis
- Denial-of-Service attack analysis
- Firewall security
- IDS/IPS concepts
- Network monitoring
- Incident containment
- Service recovery
- Security control implementation
- Defense in depth

## Project Files

- [NIST CSF Incident Report Analysis](nist-csf-incident-report-analysis.pdf) — Completed incident analysis applying the NIST CSF to an ICMP DoS security event.

## Project Context

This project was completed using a simulated cybersecurity incident. The incident analysis, NIST CSF application, security control evaluation, response planning, and recovery recommendations represent my work.
