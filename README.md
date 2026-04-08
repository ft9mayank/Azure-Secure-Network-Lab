# Azure Secure Multi-Tier Infrastructure Deployment

## 📌 Project Overview
Deployment of a secure, 2-tier infrastructure using a **Hub-and-Spoke** model. A hardened **Jumpbox** (Bastion host) gates access to a private backend Web Server, ensuring zero direct public internet exposure for sensitive resources.

---

## 🛠️ Implementation & Security Proof

### 1. Resource Inventory & Networking
Comprehensive view of the provisioned assets and the dual-subnet VNet configuration in Central India.
![Inventory](resource-group-overview.png)
![VNet Setup](vnet-config.png)
![Subnet Segmentation](vnet-config-subnets.png)

### 2. Tiered Security Policies (NSGs)
Documentation of the security layers:
- **Management Tier:** RDP restricted to authorized administrative IP only.
- **Web Tier:** Traffic strictly limited to the internal Management subnet; all direct internet inbound is denied.
![Management NSG](nsg-mgmt-rules.png)
![Web Tier NSG](nsg-web-rules.png)

### 3. Server Specifications
Verification of the Jumpbox (Public Entry) and the Web Server (Private IP only - 10.50.10.4).
![Jumpbox Specs](vm-jumpbox-specs.png)
![Web Specs](vm-web-specs.png)

### 4. Administrative Path (The "Jump")
The step-by-step process of accessing the isolated environment. Note the transition from the Public Jumpbox to the Private Web Server.

![RDP Login Screen](rdp-login-screen.png)
![RDP Login Credentials](rdp-login-credentials.png)
![Jumpbox Desktop](jumpbox-desktop.png)
![Internal Connection Success](jumpbox-desktop-rdp-succesfull.png)
![Internal Jump Initiation](internal-rdp-init.png)
![Web VM Specs in RDP](web-vm-specs-in-rdp.png)

### 5. Service Verification (IIS)
Installing the Web Server role and verifying successful service delivery via the internal network.
![IIS Installation](iis-install-progress.png)
![IIS Success Verification](iis-success-verification.png)

---

## 🚀 Key Takeaways & Skills
- **Zero-Trust Networking:** Isolated backend tiers from the public internet.
- **Security Engineering:** Implemented multi-tier NSG rules and Jumpbox patterns.
- **Cloud Administration:** Deployed Windows Server 2025 and IIS roles in a segmented environment.
