# Network Hardening Risk Assessment

## Project Overview

This project documents a security risk assessment for a simulated organization that experienced a data breach involving customer information.

The objective was to evaluate identified security vulnerabilities, select appropriate network and authentication hardening controls, and explain how those controls could reduce the likelihood of future security incidents.

## Identified Vulnerabilities

The assessment identified several weaknesses in the organization's security posture:

- Employees were sharing passwords.
- The database administrator account was still using a default password.
- Firewall rules were not configured to properly filter inbound and outbound network traffic.
- Multifactor authentication (MFA) was not implemented.

## Recommended Security Controls

### Password Policies

Password policies should establish and enforce secure password practices across the organization. This includes eliminating default credentials, discouraging password sharing, and ensuring authentication credentials are appropriately protected.

### Firewall Maintenance

Firewall rules should be regularly reviewed and maintained to control inbound and outbound network traffic. Properly configured rules can restrict unnecessary or unauthorized traffic and reduce exposure to network-based threats.

### Multifactor Authentication (MFA)

MFA adds an additional authentication layer beyond a password. If an attacker obtains or guesses a user's password, another authentication factor would still be required before access could be granted.

## Hardening Schedule

- **Firewall maintenance:** Review and maintain rules regularly and update them when security events or network changes require it.
- **Password policies:** Establish organizational requirements, continuously enforce them, and periodically review the policy.
- **MFA:** Configure for applicable accounts and maintain authentication methods after deployment.

## Security Concepts Demonstrated

- Network hardening
- Security risk assessment
- Firewall configuration principles
- Authentication security
- Multifactor authentication
- Password security
- Defense in depth
- Vulnerability remediation
- Security control selection
- Risk reduction

## Project Files

- [Network Hardening Risk Assessment](network-hardening-risk-assessment.pdf) — Completed security risk assessment and hardening recommendations.

## Project Context

This project was completed using a simulated cybersecurity scenario. The vulnerability assessment, control selection, analysis, and recommendations represent my work.
