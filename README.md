# 2024Gr14CS46
# 5G Core Network Deployment with Docker, Ansible, OVS & Monitoring Dashboard

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

---

## 🚀 Deployment Commands

### 🐳 Step 1: Free5GC Core Deployment (Docker + Ansible)

```bash
# Install dependencies
sudo apt update
sudo apt install -y git python3 python3-pip docker.io docker-compose

# Start Docker daemon
sudo systemctl start docker
sudo systemctl enable docker

# Clone the project repository
git clone https://github.com/your-username/5g-network-deployment.git
cd 5g-network-deployment/ansible-playbooks/

# Run the Ansible Playbook to deploy Free5GC containers
ansible-playbook docker-deployment.yml
```


## Part 2 : OVS and network slicing 
```bash
# Install OVS
sudo apt install -y openvswitch-switch

# Create a virtual OVS bridge
sudo ovs-vsctl add-br br-free5gc

# Create veth pairs for two slices
sudo ip link add vethA type veth peer name vethA-peer
sudo ip link add vethB type veth peer name vethB-peer

# Attach veth interfaces to OVS bridge
sudo ovs-vsctl add-port br-free5gc vethA
sudo ovs-vsctl add-port br-free5gc vethB

# Bring interfaces up
sudo ip link set dev vethA up
sudo ip link set dev vethA-peer up
sudo ip link set dev vethB up
sudo ip link set dev vethB-peer up

# Verify OVS bridge and interfaces
sudo ovs-vsctl show
```

## Part 3 : Prometheus + Grafana + cAdvisor Monitoring
``` bash
# Navigate to monitoring setup
cd ../monitoring/

# Launch services with Docker Compose
docker-compose up -d

# cAdvisor (Port 8080), Prometheus (Port 9090), Grafana (Port 3000), Node Exporter (9100)
```


  
## 📂 Final Report
[📄 Click here to view the project report](./5g_LabReport_Final.pdf)

---

## 👩‍💻 Group Members

- **Garima Singh** (202251047)  
- **Diya Garg** (202251044)  
- **Nimisha Kushwaha** (202251079)  
- **Pankaj** (202251083)


