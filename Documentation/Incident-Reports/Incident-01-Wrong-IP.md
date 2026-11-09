# Incident Report 01 – Incorrect IP Address

## 1. Incident Overview

- **Incident:** Incorrect IP address configuration
- **Affected device:** USER-PC
- **VLAN:** 30 – Users
- **Severity:** Medium
- **Category:** Network configuration error

## 2. Problem Description

USER-PC was assigned an IP address belonging to VLAN 20 instead of VLAN 30.

As a result, the device could not communicate correctly with its intended network resources.

## 3. Faulty Configuration

| Parameter | Incorrect value |
|---|---|
| IPv4 address | 192.168.20.50 |
| Subnet mask | 255.255.255.0 |
| Default gateway | 192.168.30.1 |
| DNS server | 192.168.40.10 |

### Evidence – Initial Fault

![Initial incorrect IP configuration](../Screenshots/Incident-01-Wrong-IP/01-Fault.png)

*Figure 1: USER-PC assigned an IP address from the wrong subnet.*

## 4. Root Cause

The workstation was configured with an IP address from the wrong subnet.

VLAN 30 uses the network `192.168.30.0/24`, but USER-PC was assigned an address from `192.168.20.0/24`.

## 5. Troubleshooting

1. Tested network connectivity using the `ping` command.
2. Inspected the workstation's IP configuration using `ipconfig`.
3. Checked switch VLAN assignments using `show vlan brief`.
4. Confirmed that USER-PC's switch port was correctly assigned to VLAN 30.
5. Identified the incorrect IP address as the root cause.

### Evidence – Diagnosis

![VLAN assignment verification](../Screenshots/Incident-01-Wrong-IP/02-Diagnosis.png)

*Figure 2: Switch VLAN configuration confirms that USER-PC's port belongs to VLAN 30.*

## 6. Corrective Action

Updated USER-PC's configuration:

| Parameter | Correct value |
|---|---|
| IPv4 address | 192.168.30.50 |
| Subnet mask | 255.255.255.0 |
| Default gateway | 192.168.30.1 |
| DNS server | 192.168.40.10 |

## 7. Verification

- Default gateway ping: Successful
- Server connectivity: Successful
- Network communication: Restored

### Evidence – Successful Recovery

![Corrected IP configuration and successful connectivity](../Screenshots/Incident-01-Wrong-IP/03-Verification.png)

*Figure 3: Correct IP configuration and successful connectivity tests after remediation.*

## 8. Lessons Learned

- Devices must use IP addresses belonging to their assigned VLAN subnet.
- Incorrect IP addressing can prevent communication with network resources.
- Verifying IP configuration is an essential first step in network troubleshooting.
- Checking VLAN assignments helps distinguish IP configuration issues from switching issues.