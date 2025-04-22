# 2024Gr14CS462
# 🚀 5G Core Network Deployment with Docker, Ansible, OVS & Monitoring Dashboard

This project demonstrates the deployment of a 5G Core Network based on **Free5GC**, containerized via **Docker**, automated with **Ansible**, extended using **Open vSwitch (OVS)** for network slicing, and monitored using **Prometheus** and **Grafana**.

## 📦 Components Used

- **Free5GC Core Functions**: AMF, SMF, UPF, HSS, WebUI, PCRF, MongoDB
- **Virtualization**: Docker + Docker Compose
- **Automation**: Ansible
- **Network Slicing**: Open vSwitch (OVS) with veth pairs and VLANs
- **Monitoring**: Prometheus, Grafana, cAdvisor

## 🛠️ Features Implemented

### ✅ Phase 1: Core Network Deployment (Docker + Ansible)
- Ansible playbook to deploy Free5GC containers
- Automated container orchestration
- Logs validation (AMF registered with NRF)

### ✅ Phase 2: Network Slicing via OVS
- Created OVS bridge and veth pairs
- VLAN-based logical slices (Slice-1: VLAN 10, Slice-2: VLAN 20)
- Packet routing & ping tests across slices

### ✅ Phase 3: Monitoring Dashboard
- Prometheus + Grafana setup
- cAdvisor for container insights
- Dashboards with CPU, memory usage, and component metrics

## 📸 Screenshots
![Grafana Dashboard](./screenshots/grafana-dashboard.png)
![cAdvisor UI](./screenshots/cadvisor-ui.png)

## 📂 Final Report
[📄 Read the full report here](./report/5g_LabReport_Final.pdf)
