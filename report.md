# Cybersecurity Task 3: Vulnerability Scan Report

## 1. Executive Summary

[cite_start]This report outlines the results of a vulnerability assessment performed on a host PC, as required by the Elevate Labs Cybersecurity Internship program. [cite: 2] [cite_start]The objective was to use a vulnerability scanner to identify common security risks on a personal computer. [cite: 6] The scan was conducted using OpenVAS (Greenbone Security Manager) and successfully identified 82 total results, including two notable medium-severity vulnerabilities that require attention.

## 2. Scan Details

* **Scanning Tool**: OpenVAS Community Edition 24.10.6
* **Target Host**: `192.168.56.1` (Host PC on VirtualBox Host-Only Network)
* **Scan Type**: Full and fast
* **Scan Date**: September 25, 2025

## 3. Medium-Severity Vulnerability Findings

[cite_start]The following medium-severity vulnerabilities were identified as the most critical findings from the assessment. [cite: 16]

### Vulnerability: SSL/TLS: Deprecated TLSv1.0 and TLSv1.1 Protocol Detection

* **Severity**: Medium
* **CVSS Score**: 6.3
* **Description**: The scan detected that a service on the host machine supports outdated and insecure cryptographic protocols, specifically TLS version 1.0 and 1.1. These protocols have known vulnerabilities that could allow an attacker to intercept or manipulate sensitive data.
* **Affected Asset**: Port `3389/tcp` on host `192.168.56.1`. This port is commonly used for Microsoft Remote Desktop Protocol (RDP).
* **Recommended Remediation**: Reconfigure the system's registry settings to disable TLS 1.0 and TLS 1.1 system-wide. Enforce the use of modern, secure protocols such as TLS 1.2 and TLS 1.3 to protect data in transit.

---

### Vulnerability: DCE/RPC and MSRPC Services Enumeration Reporting

* **Severity**: Medium
* **CVSS Score**: 5.8
* **Description**: The scanner was able to remotely query the Microsoft Remote Procedure Call (MSRPC) service to enumerate information. This allows a potential attacker to gather details about running services, network interfaces, and other system information, which can be used to plan a more targeted attack.
* **Affected Asset**: Port `135/tcp` on host `192.168.56.1`.
* **Recommended Remediation**: Implement stricter firewall rules to limit access to the RPC Endpoint Mapper service on port 135. Access should be restricted to only trusted hosts or management subnets to reduce the system's exposure to network reconnaissance.

## 4. Scan Results Screenshot

[cite_start]The following screenshot shows the summary of the scan results from the OpenVAS dashboard. [cite: 17]




## 5. Conclusion

The vulnerability assessment was successful in identifying key areas for security improvement on the target host. Prioritizing the remediation of the medium-severity findings by disabling deprecated protocols and hardening network services will significantly improve the overall security posture of the system.
