# SOC Home Lab with Splunk Enterprise

## Project Overview

This project demonstrates the creation of a Security Operations Center (SOC) Home Lab using Splunk Enterprise, Sysmon, Splunk Universal Forwarder, and Atomic Red Team.

The lab is designed to simulate real-world cyber attacks, collect Windows telemetry, forward logs to Splunk, and perform detection and investigation using MITRE ATT&CK techniques.

The primary objective of this project is to develop practical SOC analyst skills by building a complete home lab, simulating adversary techniques, detecting malicious activities, and investigating security events using Splunk Enterprise.


## Objectives

- Build a functional SOC Home Lab for security monitoring and threat detection.
- Collect Windows telemetry using Sysmon.
- Forward Windows logs using Splunk Universal Forwarder.
- Monitor logs with Splunk Enterprise.
- Simulate attacks using Atomic Red Team.
- Detect malicious activities using Splunk SPL queries.
- Map attacks to the MITRE ATT&CK Framework.
- Practice SOC investigation techniques.
- Document findings in professional investigation reports.

## Lab Architecture

The SOC Home Lab consists of a Kali Linux virtual machine hosting Splunk Enterprise and a Windows 10 virtual machine configured with Sysmon and the Splunk Universal Forwarder. Atomic Red Team is used to simulate MITRE ATT&CK techniques, while Splunk collects, indexes, and visualizes telemetry for investigation.

### Architecture Diagram

![SOC Home Lab Architecture](images/lab-architecture.png)

## Technologies Used

| Technology | Purpose |
| ---------- | ------- |
| Splunk Enterprise | Security Information and Event Management (SIEM) |
| Sysmon | Windows system activity logging |
| Splunk Universal Forwarder | Forwards Windows logs to Splunk |
| Atomic Red Team | Simulates MITRE ATT&CK techniques |
| Windows 10 | Target endpoint for attack simulation |
| Kali Linux | Hosts Splunk Enterprise SIEM |
| VMware Workstation | Virtualization platform |
| PowerShell | Executes attack simulation scripts and automation |
| MITRE ATT&CK Framework | Maps adversary behaviors and techniques |
| Git & GitHub | Version control, collaboration, and project documentation |
| Visual Studio Code | Documentation and project management |

## Lab Environment

| Component | Details |
| --------- | ------- |
| Host Machine | HP ProBook 430 G8 |
| Processor | Intel Core i5-1135G7 |
| RAM | 16 GB DDR4 |
| Hypervisor | VMware Workstation |
| SIEM Server | Kali Linux (Virtual Machine) hosting Splunk Enterprise |
| Endpoint | Windows 10 (Virtual Machine) |
| SIEM Platform | Splunk Enterprise |
| Log Collection | Sysmon + Splunk Universal Forwarder |
| Attack Simulation | Atomic Red Team |
| Network Mode | NAT |

## Network Topology

The SOC Home Lab is deployed in VMware Workstation using a NAT virtual network. The environment consists of two virtual machines: a Kali Linux VM running Splunk Enterprise and a Windows 10 VM configured with Sysmon, Splunk Universal Forwarder, and Atomic Red Team.

Sysmon collects detailed Windows endpoint telemetry, while the Splunk Universal Forwarder securely forwards the generated logs to the Splunk Enterprise server on TCP port 9997. Splunk indexes the incoming events and provides a web interface accessible through HTTP on port 8000 for monitoring, searching, and investigation.

All virtual machines communicate over the same NAT network, allowing secure connectivity without exposing the lab directly to the external network.

                 HP ProBook 430 G8
                  (Host Machine)
                         │
                  Web Browser
               (Splunk Web UI)
                  HTTP :8000
                         │
                         ▼

            ┌──────────────────────┐
            │    Kali Linux VM     │
            │                      │
            │ Splunk Enterprise    │
            │ Indexer + Web UI     │
            └─────────▲────────────┘
                      │
          TCP 9997 (Forwarded Logs)
                      │
                      │
            ┌─────────┴────────────┐
            │    Windows 10 VM     │
            │                      │
            │ Sysmon               │
            │ Splunk UF            │
            │ Atomic Red Team      │
            └──────────────────────┘


Network Communication

| Source          | Destination   | Protocol   | Port  | Purpose                                              |
| --------------- | ------------- | ---------- | ----- | ---------------------------------------------------- |
| Windows 10 VM   | Kali Linux VM | TCP        | 9997  | Forward Sysmon logs using Splunk Universal Forwarder |
| Host Browser    | Kali Linux VM | HTTP       | 8000  | Access Splunk Enterprise Web UI                          |
| Atomic Red Team | Windows 10 VM | PowerShell | Local | Execute MITRE ATT&CK simulations                           |


Virtual Machines

| Machine       | Role                                                    |
| ------------- | ------------------------------------------------------- |
| Kali Linux VM | Splunk Enterprise Server (Indexer & Web UI)             |
| Windows 10 VM | Endpoint for attack simulation and telemetry collection |
| Host Computer  | SOC Analyst workstation for accessing Splunk            |

This topology enables centralized log collection, attack simulation, and security monitoring in an isolated virtual environment.

## Data Flow

## Installation Guide

## Attack Simulations

## Splunk Detection Queries

## Investigation Reports

## Skills Demonstrated

## Project Structure

## Future Improvements

## Acknowledgements
