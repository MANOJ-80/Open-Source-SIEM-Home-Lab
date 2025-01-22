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
```
### Step 3: Install Elastic Stack
### Install Elasticsearch

1. Add the Elasticsearch GPG key and repository.
2. Install Elasticsearch:

```bash
sudo apt install elasticsearch -y
```
3. Configure Elasticsearch by editing `/etc/elasticsearch/elasticsearch.yml`.
4. Start and enable Elasticsearch:

```bash
sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch
```
### Install Logstash

1. Install Logstash:
```bash
sudo apt install logstash -y
```
2. Create a pipeline configuration file in `/etc/logstash/conf.d/`.
3. Start and enable Logstash:

```bash
sudo systemctl start logstash
sudo systemctl enable logstash
```
### Install Kibana

1. Install Kibana:

```bash
sudo apt install kibana -y
```
2. Configure Kibana in `/etc/kibana/kibana.yml`.
3. Start and enable Kibana:

```bash
sudo systemctl start kibana
sudo systemctl enable kibana
```
4. Access Kibana at http://<vm_ip>:5601.

### Install Filebeat

1. Install Filebeat:

```bash
sudo apt install filebeat -y
```
2. Configure Filebeat to send logs to Logstash.
3. Start and enable Filebeat:

```bash
sudo systemctl start filebeat
sudo systemctl enable filebeat
```
### Step 4: Integrate Suricata

1.Install Suricata:

```bash
sudo apt install suricata -y
```
2. Configure Suricata to monitor network traffic and output logs to Filebeat.

### Step 5: Generate Logs

1. Use the secondary VM to generate log traffic:

```bash
sudo apt install rsyslog
```
2. Configure rsyslog to forward logs to the ELK Stack VM.

### Step 6: Test and Analyze Logs

1. Open Kibana and navigate to the "Discover" tab.
2. Verify that logs are indexed correctly in Elasticsearch.
3. Create custom dashboards and visualizations for your logs.

### Contributing   
Contributions are welcome! If you have suggestions, bug fixes, or additional features, feel free to submit a pull request.

### License
This project is licensed under the MIT License.
