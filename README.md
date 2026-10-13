# Dominic De La Fuente | IT Operations & Infrastructure Portfolio

**Location:** San Antonio, TX | **Targeting:** Data Center Technician / Production Operations Engineer
**Contact:** Dominicdel03@gmail.com 
**Certifications:** Google IT Support Professional Certificate | CompTIA A+ (Expected Nov 2026)

---

## 🛠️ Infrastructure Project 1: Bare-Metal Linux Server Deployment
**Objective:** Provisioned and deployed a custom bare-metal Linux server hosting four concurrent production environments, requiring dynamic resource allocation and active break-fix troubleshooting.

### Hardware & OS Specifications
| Component | Specification / Allocation |
| :--- | :--- |
| **Operating System** | Ubuntu Server 22.04 LTS (Headless) |
| **Compute** | Dynamic CPU threading across 4 isolated environments |
| **Memory Allocation** | Hard-capped RAM limits per instance to prevent overallocation |
| **Network** | Static IP allocation with dedicated port forwarding |

### 🔍 Break-Fix Log: Resolving Out-Of-Memory (OOM) Panics
**Symptom:** Server experienced intermittent unresponsiveness; background environments were crashing under load.
**Diagnostics & Resolution:**
1. Accessed the system via SSH and utilized `top` and `htop` to identify rogue processes consuming 100% of memory resources.
2. Checked system logs using `dmesg | grep -i oom` to confirm the Linux Out-Of-Memory killer was terminating active instances.
3. Modified background process limits and reallocated dedicated RAM pools to stabilize the system.

---

## 🌐 Infrastructure Project 2: Physical Network Architecture
**Objective:** Designed and implemented a low-latency network infrastructure anchoring high-performance endpoints. 

### Network Topology Diagram
*(Rendered via Mermaid.js)*
```mermaid
graph TD;
    A[AT&T Fiber Gateway] -->|Passthrough Mode| B(TP-Link Mesh Primary Router);
    B -->|Cat 6 Ethernet| C[Workstation / Test Bench];
    B -->|Cat 6 Ethernet| D[Bare-Metal Linux Server];
    B -->|Wireless Backhaul| E(TP-Link Mesh Node 2);
    B -->|Wireless Backhaul| F(TP-Link Mesh Node 3);
