# DoS SYN Flood Attack Analysis

## Project Overview

This project documents my analysis of a simulated network security incident involving a web server experiencing a service interruption. Using Wireshark packet-capture data, I analyzed TCP traffic to determine the type of attack, identify the source of the abnormal traffic, and explain how the attack affected legitimate users.

## Incident Summary

Employees began experiencing connection timeout errors when attempting to access the company's website.

Analysis of the packet capture showed a large number of TCP SYN packets originating from a single IP address:

**203.0.113.0**

Initially, the web server continued processing legitimate employee connections. As the SYN requests continued in rapid succession, the server became overwhelmed and eventually could no longer properly respond to legitimate connection requests.

Based on the network traffic, I identified the incident as a:

**Denial-of-Service (DoS) SYN Flood Attack**

## Technical Analysis

A normal TCP connection uses a three-way handshake:

1. **SYN** - The client requests a connection with the server.
2. **SYN-ACK** - The server acknowledges the request and reserves resources for the connection.
3. **ACK** - The client acknowledges the server's response and completes the connection.

During the incident, the attacking system repeatedly sent SYN packets to the web server.

Instead of normal TCP connections being established, the increasing volume of SYN requests consumed server resources. As the attack continued, legitimate users began experiencing failed connections and timeout errors.

Because the malicious traffic observed in this scenario originated from a single source, the incident was classified as a **DoS attack rather than a Distributed Denial-of-Service (DDoS) attack**.

## Indicators Observed

- Repeated TCP SYN packets
- Source IP: `203.0.113.0`
- Destination web server: `192.0.2.1`
- Destination port: `443`
- Increasing volume of connection requests
- RST/ACK responses as legitimate connections began failing
- HTTP 504 Gateway Time-out errors
- Loss of availability for legitimate users

## Impact

The SYN flood exhausted the web server's ability to handle legitimate connection requests.

This resulted in:

- Website availability issues
- Employee connection failures
- Connection timeout errors
- Disruption of normal business operations

## Initial Response

The affected server was temporarily taken offline to allow it to recover.

The firewall was also configured to block the IP address generating the abnormal traffic. However, IP blocking alone is not a complete long-term defense because an attacker may change or spoof source addresses.

## Security Skills Demonstrated

- Network traffic analysis
- Wireshark packet analysis
- TCP/IP protocol analysis
- TCP three-way handshake analysis
- DoS attack identification
- SYN flood identification
- Incident investigation
- Network troubleshooting
- Security incident documentation

## Key Takeaway

This investigation demonstrated how abnormal TCP behavior can be identified through packet analysis. By comparing legitimate TCP connections with the attack traffic, I was able to identify a SYN flood pattern and determine how the excessive connection requests affected the availability of the web server.
