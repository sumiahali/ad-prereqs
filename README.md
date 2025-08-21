# Preparing Active Directory Infrastructure: Prerequisites

This tutorial provides the steps to prepare Active Directory (AD) infrastructure in Azure.

## Environments and Technologies Used

- **Microsoft Azure**
- **Windows Server 2022** (Domain Controller)
- **Windows 11** (Client machine)
- **Windows App** (For management and testing)
- **PowerShell** (For configuration and testing)

## Operating Systems Used

- **Windows Server 2022** (for Domain Controller VM)
- **Windows 11** (for Client machine VM)

## Deployment and Configuration Steps

### Setup Domain Controller in Azure
#### Prepare AD Infrastructure in Azure:
1. **Create a Resource Group**
   - In the Azure portal, create a new resource group to house all resources related to the Active Directory setup.
   <p>
   <img width="420" height="365" alt="image" src="https://github.com/user-attachments/assets/b5522808-b95b-447d-93a3-8beeec8d5b2d" />
   </p>

2. **Create a Virtual Network and Subnet**
   - Set up a virtual network and subnets for communication between VMs.
   <p>
   <img width="692" height="598" alt="image" src="https://github.com/user-attachments/assets/6c6739c5-22af-4c28-a709-b42114ede5b1" />
   </p>

3. **Create the Domain Controller VM (Windows Server 2022)**
   - Set up a Windows Server 2022 VM as the Domain Controller and name it "dc-1".
   - Assign a static private IP to the NIC for stable network configuration.
  <p>
  <img width="692" height="598" alt="image" src="https://github.com/user-attachments/assets/4e221a7c-f4b2-4a0c-8f20-73f4335352d0" />
  <img width="692" height="598" alt="image" src="https://github.com/user-attachments/assets/467ec651-cf25-4f55-a5a5-33e92d2e6a39" />
  <img width="692" height="598" alt="image" src="https://github.com/user-attachments/assets/233d4cf4-e8b2-4030-ad30-bdba5f2304e6" />
  <img width="522" height="598" alt="image" src="https://github.com/user-attachments/assets/9efe00ab-980e-4370-8875-ad7d893e8f5c" />
  </p>

4. **Log into the VM and disable the Windows Firewall**
   - Log into the Domain Controller and temporarily disable the Windows Firewall for testing.
  <p>
  <img width="820" height="450" alt="image" src="https://github.com/user-attachments/assets/8cab3bbb-58ae-44bf-83e0-e1c060016cce" />
  <img width="750" height="519" alt="image" src="https://github.com/user-attachments/assets/1119067e-3ffc-49be-9eb3-32f5c2de0de6" />
  <img width="796" height="910" alt="image" src="https://github.com/user-attachments/assets/4d287634-2855-4a29-9b1e-c3d0fc220082" />
  <img width="796" height="908" alt="image" src="https://github.com/user-attachments/assets/3c5888c8-3e84-4471-b5e9-13198d912e54" />
  <img width="752" height="513" alt="image" src="https://github.com/user-attachments/assets/0c50a0bb-78b8-4fba-8ce1-14e60a200e2f" />
  </p>
---

### Setup client-1 in Azure
1. **Create the Client VM (Windows 11)**
   - Set up a Windows 11 VM as the Client machine and name it "client-1" (ensure both VMs are in the same network and region).
<p>
<img width="520" height="620" alt="image" src="https://github.com/user-attachments/assets/1cffd623-b0c9-4034-af13-e7d0b19f330f" />
</p>

2. **Set client-1’s DNS to dc-1’s Private IP**
   - Configure "client-1" to use "dc-1’s" private IP as its DNS server.
<p>
<img width="1066" height="574" alt="image" src="https://github.com/user-attachments/assets/332b9f84-3d14-47bd-bebd-3b6fc8826b15" />
<img width="1098" height="485" alt="image" src="https://github.com/user-attachments/assets/7254caf8-cb28-4418-9280-27f23a8596a8" />
</p>

3. **Restart client-1 and log in**
   - Restart "client-1" to apply the DNS settings.
   - Log into "client-1" to check the connection.
<p>
<img width="1382" height="305" alt="image" src="https://github.com/user-attachments/assets/43ffbf26-c297-4b53-974d-e24cf2228ba9" />
<img width="957" height="597" alt="image" src="https://github.com/user-attachments/assets/1b5d967e-b3f4-46b7-be8c-684422b4a704" />
</p>

4. **Ping dc-1’s private IP from client-1 and verify the connection**
   - Ping "dc-1" from "client-1" to confirm the connection is successful and verify network communication.
<p>
<img width="858" height="478" alt="image" src="https://github.com/user-attachments/assets/5bb4860d-7edb-4b2a-8116-51b564e0e032" />
</p>

6. **Check DNS Settings on client-1**
   - Run `ipconfig /all` on "client-1" to verify it uses "dc-1’s" IP for DNS.
<p>
<img width="736" height="552" alt="image" src="https://github.com/user-attachments/assets/b4114cf5-b6cf-45fb-91bf-ecf17233f914" />
</p>
