# Windows Attack Analysis Lab

## Overview

This project documents a forensic analysis of a suspected intrusion on a Windows-based host. The investigation used Windows Event Viewer and Wireshark to analyze system logs and network traffic, identify indicators of compromise, and reconstruct the likely sequence of attacker activity.

This project was completed as part of IS 3523 at the University of Texas at San Antonio.

## Objectives

- Analyze Windows application and security event logs
- Investigate suspicious network traffic using Wireshark
- Identify indicators of compromise
- Correlate host-based and network-based evidence
- Reconstruct an attack timeline
- Identify potential attacker techniques and behavior
- Recommend remediation and containment steps

## Tools Used

- Windows Event Viewer
- Wireshark
- Windows Event Logs (.evt)
- Packet Capture (PCAP/PCAPNG)
- MITRE ATT&CK

## Methodology

The investigation followed a layered analysis process:

1. Initial log review
2. Network traffic triage
3. Payload analysis
4. Correlation of host and network evidence
5. Attack timeline reconstruction
6. Remediation recommendations

## Key Findings

### Windows Event Log Analysis

The application logs contained suspicious Windows Management Instrumentation (WMI) activity involving a `CmdTriggerConsumer` registered under the LocalSystem account.

Additional WinMgmt events were reviewed as potential indicators of system modification or tampering.

### Network Traffic Analysis

Wireshark was used to analyze the provided packet capture.

The investigation identified:

- Packets containing the keyword `password`, indicating potential plaintext credential exposure
- Command-related traffic containing `cmd`
- A TCP stream containing an `MZ` header associated with a Windows Portable Executable (PE) file
- Unusual network activity between internal hosts

### Attack Timeline

The evidence was correlated to reconstruct a likely attack sequence involving:

1. Suspicious WMI activity
2. Abnormal TCP connection activity
3. Credential exposure
4. Command-related network traffic
5. Transfer of a Windows executable
6. Potential post-exploitation activity

## Remediation

Recommended actions included:

- Isolating the affected system from the network
- Resetting credentials associated with the compromised host
- Removing unauthorized WMI persistence mechanisms
- Monitoring unusual TCP connection activity
- Detecting executable transfers across the network
- Using encrypted authentication protocols
- Improving network segmentation and log monitoring

## Skills Demonstrated

- Windows Event Log Analysis
- Network Traffic Analysis
- Wireshark
- Windows Troubleshooting
- TCP/IP Analysis
- WMI Analysis
- Incident Response
- Attack Timeline Reconstruction
- Cybersecurity Investigation
- Technical Documentation

## Disclaimer

This project was completed in a controlled academic/lab environment for educational purposes. No unauthorized systems were accessed or tested.

## References

- Microsoft Windows Event ID Documentation
- Microsoft Windows Management Instrumentation Documentation
- Wireshark Documentation
- NIST SP 800-61
- MITRE ATT&CK
