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
   <img width="892" height="798" alt="image" src="https://github.com/user-attachments/assets/6c6739c5-22af-4c28-a709-b42114ede5b1" />
   </p>

3. **Create the Domain Controller VM (Windows Server 2022)**
   - Set up a Windows Server 2022 VM as the Domain Controller.
   - Assign a static private IP to the NIC for stable network configuration.
  <p>
  <img width="1480" height="1456" alt="image" src="https://github.com/user-attachments/assets/4e221a7c-f4b2-4a0c-8f20-73f4335352d0" />
  <img width="2210" height="1178" alt="image" src="https://github.com/user-attachments/assets/467ec651-cf25-4f55-a5a5-33e92d2e6a39" />
  <img width="2524" height="1260" alt="image" src="https://github.com/user-attachments/assets/233d4cf4-e8b2-4030-ad30-bdba5f2304e6" />
  <img width="1160" height="1488" alt="image" src="https://github.com/user-attachments/assets/9efe00ab-980e-4370-8875-ad7d893e8f5c" />
  </p>

4. **Log into the VM and disable the Windows Firewall**
   - Log into the Domain Controller and temporarily disable the Windows Firewall for testing.
  <p>
  <img width="820" height="450" alt="image" src="https://github.com/user-attachments/assets/8cab3bbb-58ae-44bf-83e0-e1c060016cce" />
  <img width="1500" height="1038" alt="image" src="https://github.com/user-attachments/assets/1119067e-3ffc-49be-9eb3-32f5c2de0de6" />
  <img width="796" height="910" alt="image" src="https://github.com/user-attachments/assets/4d287634-2855-4a29-9b1e-c3d0fc220082" />
  <img width="796" height="908" alt="image" src="https://github.com/user-attachments/assets/3c5888c8-3e84-4471-b5e9-13198d912e54" />
  <img width="1504" height="1026" alt="image" src="https://github.com/user-attachments/assets/0c50a0bb-78b8-4fba-8ce1-14e60a200e2f" />
  </p>
---

### Setup Client-1 in Azure
1. **Create the Client VM (Windows 11)**
   - Set up a Windows 11 VM as the Client machine.
<p>
<img width="1124" height="1474" alt="image" src="https://github.com/user-attachments/assets/1cffd623-b0c9-4034-af13-e7d0b19f330f" />
</p>
