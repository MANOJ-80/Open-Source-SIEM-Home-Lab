# Open Source SIEM Home Lab

A step-by-step guide to building your own Security Information and Event Management (SIEM) home lab using Elastic Stack and Suricata for network-based intrusion detection. This project is ideal for cybersecurity enthusiasts who want hands-on experience in log collection, monitoring, and threat detection.

## Features

* **Centralized Log Collection**: Collect and index logs from various sources using Elastic Stack.
* **Custom Alerts**: Configure and visualize alerts in Kibana.
* **Intrusion Detection**: Integrate Suricata for network-based monitoring.
* **Scalable Setup**: Modular design to add more log sources and tools.

## Tools Used

* **Elastic Stack**:
   * Elasticsearch
   * Logstash
   * Kibana
   * Filebeat
* **Suricata**: Open-source network-based intrusion detection system (IDS).
* **Ubuntu Server**: For hosting the Elastic Stack and log sources.
* **Virtualization Software**: VirtualBox or VMware for creating isolated environments.

## Prerequisites

* A computer with at least 4GB RAM and 100GB disk space.
* Basic knowledge of Linux, networking, and cybersecurity.
* Virtualization software (e.g., VirtualBox, VMware).
* Internet connection for downloading required software.

## Installation

Follow the steps below to set up the SIEM home lab:

### Step 1: Install and Set Up Virtualization Software

1. Install VirtualBox or VMware on your system.
2. Create virtual machines for:
   * The ELK Stack (Elasticsearch, Logstash, Kibana, Filebeat).
   * A log source to generate traffic.

### Step 2: Set Up Ubuntu Virtual Machine

1. Download the Ubuntu Server ISO from the official website.
2. Create a new VM in your virtualization software:
   * Allocate 2 CPUs, 4GB RAM, and 50GB storage.
   * Mount the Ubuntu ISO and complete the installation.
3. Update the system:

```bash
sudo apt update && sudo apt upgrade -y
