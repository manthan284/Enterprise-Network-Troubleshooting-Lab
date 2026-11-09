# Enterprise Network Troubleshooting Lab

A hands-on enterprise networking and troubleshooting project built using Cisco Packet Tracer. This lab demonstrates common network failures, systematic fault diagnosis, configuration recovery, and connectivity verification.

## Project Overview

This project simulates an enterprise network with multiple VLANs, inter-VLAN routing, DHCP, DNS, HTTP services, access control lists, and switch port security.

Seven network troubleshooting incidents were intentionally introduced, diagnosed, and resolved. Each incident includes a fault scenario, diagnosis, corrective actions, verification screenshots, and separate Packet Tracer fault/fixed files.

## Objectives

- Understand enterprise network architecture.
- Configure VLANs and trunk links.
- Implement inter-VLAN routing using router-on-a-stick.
- Configure DHCP, DNS, and HTTP services.
- Troubleshoot network connectivity issues.
- Identify and resolve ACL and port security misconfigurations.
- Document incidents using a structured troubleshooting approach.

## Technologies and Tools

- Cisco Packet Tracer
- Networking: VLANs, trunking, inter-VLAN routing, IPv4
- Services: DHCP, DNS, HTTP
- Security: ACLs, switch port security, sticky MAC
- Troubleshooting: ping, ipconfig, show commands
- Documentation: Markdown and GitHub

## Network Design

### VLAN and IP Addressing

| VLAN | Department | Network         | Default Gateway |
| ---- | ---------- | --------------- | --------------- |
| 10   | Admin      | 192.168.10.0/24 | 192.168.10.1    |
| 20   | IT         | 192.168.20.0/24 | 192.168.20.1    |
| 30   | Users      | 192.168.30.0/24 | 192.168.30.1    |
| 40   | Servers    | 192.168.40.0/24 | 192.168.40.1    |

### Network Components

- Router R1 – Inter-VLAN routing using router-on-a-stick.
- Switch SW1 – VLAN configuration, trunking, and port security.
- End devices – Admin, IT, and User PCs.
- Server SRV1 – DHCP, DNS, and HTTP services.

### Server Configuration

- Server IP: `192.168.40.10`
- DNS record: `intranet.lab`
- Web service: Internal HTTP website
- DHCP pool: `USERS`
- DHCP network: `192.168.30.0/24`

## Troubleshooting Scenarios

Seven incidents were successfully reproduced, diagnosed, and resolved.

| Incident Report | Original Scenario | Fault                        |
| --------------- | ----------------- | ---------------------------- |
| 01              | Scenario 01       | Wrong IP Address             |
| 02              | Scenario 02       | VLAN Mismatch                |
| 03              | Scenario 03       | Trunk Allowed VLAN Failure   |
| 04              | Scenario 04       | Router Subinterface Shutdown |
| 05              | Scenario 05       | DHCP Pool Deleted            |
| 06              | Scenario 06       | ACL Misconfiguration         |
| 07              | Scenario 07       | Port Security Violation      |

**Note:** Original Packet Tracer scenario numbers are retained in the project folders. Incident report numbers are sequential for easier documentation.

## Repository Structure

```text
Enterprise-Network-Troubleshooting-Lab/
│
├── README.md
│
├── Packet-Tracer-Files/
│   ├── Enterprise_Network_Troubleshooting_Lab_Baseline.pkt
│   ├── Scenario-01-Wrong-IP/
│   ├── Scenario-03-VLAN-Mismatch/
│   ├── Scenario-04-Trunk-Failure/
│   ├── Scenario-05-Subinterface-Shutdown/
│   ├── Scenario-06-DHCP-Failure/
│   ├── Scenario-07-ACL-Misconfiguration/
│   └── Scenario-08-Port-Security/
│
├── Documentation/
│   ├── Incident-Reports/
│   └── Screenshots/
│
└── Experiments/
```

Each scenario folder contains separate fault and fixed `.pkt` files.

## Incident Documentation

Detailed incident reports and screenshots are available in:

- `Documentation/Incident-Reports/`
- `Documentation/Screenshots/`

Each report covers:

1. Incident overview
2. Symptoms and impact
3. Fault identification
4. Root cause analysis
5. Corrective actions
6. Verification and results

## How to Use This Project

1. Download or clone this repository.
2. Open Cisco Packet Tracer.
3. Navigate to `Packet-Tracer-Files/`.
4. Open the baseline file to explore the working network.
5. Open a scenario's `Fault` file to reproduce the issue.
6. Refer to the corresponding incident report for diagnosis and resolution.
7. Open the `Fixed` file to inspect the corrected configuration.

## Useful Troubleshooting Commands

```text
show vlan brief
show interfaces trunk
show ip interface brief
show running-config
show ip route
show access-lists
show port-security interface fastEthernet0/3
show port-security address
show ip dhcp pool
ping <destination-ip>
ipconfig /all
```

## Key Learning Outcomes

- Practiced systematic network troubleshooting.
- Diagnosed VLAN and trunk configuration errors.
- Resolved inter-VLAN routing failures.
- Recreated and verified DHCP configurations.
- Identified ACL-related connectivity restrictions.
- Investigated port security violations and sticky MAC learning.
- Documented technical incidents with evidence and recovery steps.

## Project Status

**Completed:** Seven validated troubleshooting scenarios, corresponding incident reports, screenshots, and Packet Tracer fault/fixed files.

## Disclaimer

This project is created for educational purposes in a simulated Cisco Packet Tracer environment. All incidents were intentionally introduced to practice network troubleshooting and security concepts.
