# DNS and ICMP Network Traffic Analysis

## Project Overview

This project documents my analysis of a simulated network incident involving a website that could not be reached because of a DNS communication failure.

I analyzed network traffic captured with `tcpdump` to identify the protocols involved, determine where communication was failing, and develop a possible explanation for the incident.

## Scenario

Customers reported that they were unable to access the website `www.yummyrecipesforme.com` and received a "destination port unreachable" error after waiting for the website to load.

I reproduced the issue and analyzed the network traffic using `tcpdump`.

## Tools and Technologies

- tcpdump
- DNS
- UDP
- ICMP
- TCP/IP
- Linux

## Traffic Analysis

The packet capture showed repeated DNS requests for the A record of `yummyrecipesforme.com`.

The DNS queries were sent using UDP to the DNS server on port 53. Instead of receiving the expected DNS response, ICMP packets were returned with the following error:

`udp port 53 unreachable`

Because port 53 is used by DNS, this indicated that the DNS service could not be reached through UDP.

## Key Findings

- DNS requests were being transmitted using UDP.
- The requests attempted to reach UDP port 53 on the DNS server.
- ICMP returned "port unreachable" messages.
- The DNS lookup could not complete.
- Without successful DNS resolution, the client could not obtain the IP address needed to reach the website.

## Incident Analysis

The first observed request occurred at approximately 13:24:32.

Customers reported receiving a "destination port unreachable" message when attempting to access the website. I reproduced the same issue and used `tcpdump` to inspect the network traffic.

The capture showed UDP packets being sent to the DNS server on port 53. ICMP responses then reported that UDP port 53 was unreachable.

Based on the available evidence, the DNS service may have been unavailable, or network traffic to UDP port 53 may have been blocked.

The packet capture alone does not establish the exact root cause, so additional investigation would be required.

## Recommended Next Steps

The next step would be to determine why UDP port 53 cannot be reached. This investigation should include:

- Verify that the DNS service is running and responding.
- Review firewall rules affecting UDP port 53.
- Check DNS server configuration.
- Review system and network logs for additional errors.
- Test DNS connectivity after corrective action.
- Continue monitoring network traffic to verify that DNS requests receive valid responses.

## Skills Demonstrated

This project demonstrates my ability to:

- Analyze network traffic using tcpdump
- Interpret UDP and ICMP traffic
- Recognize DNS traffic using port 53
- Analyze DNS A-record queries
- Interpret ICMP "port unreachable" errors
- Troubleshoot network service availability
- Separate confirmed evidence from possible root causes
- Document cybersecurity incident findings

## Conclusion

The investigation identified a DNS communication failure involving UDP port 53. ICMP error responses showed that DNS requests could not reach the required service, preventing successful domain-name resolution.

Further investigation of the DNS service, firewall configuration, and network configuration would be required to determine the exact root cause.
