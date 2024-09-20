# Active Directory Lab Setup on VirtualBox: Configuring Domain Controller and Client Machine

## Objective
This project provides a step-by-step guide to setting up an Active Directory (AD) lab using VirtualBox. The lab involves creating a **Windows Server 2019** virtual machine configured as a **Domain Controller (DC)** and a **Windows 10 client** machine. The project demonstrates AD, DHCP, DNS configuration, and automation of user creation using PowerShell, offering hands-on experience for understanding how AD and Windows networking work in a virtual environment.

## Skills Learned
- Setting up and configuring a Windows Server 2019 Domain Controller.
- Installing and managing Active Directory Domain Services (AD DS).
- Configuring DHCP, DNS, and network services in VirtualBox.
- Automating user creation in Active Directory using PowerShell.
- Joining Windows 10 client machines to a domain and verifying network connectivity.

## Tools Used
- **VirtualBox**: For creating and managing virtual machines.
- **Windows Server 2019**: Domain controller setup for Active Directory services.
- **Windows 10**: Client machine for joining the domain.
- **PowerShell**: Automates user creation in Active Directory.
- **Routing and Remote Access Service (RRAS)**: For enabling NAT.
- **DHCP Server**: Provides IP addresses to internal network clients.

## Steps and Screenshots

### Step 1: Installing VirtualBox and Creating Virtual Machines
- Download and install VirtualBox along with its Extension Pack for additional features (e.g., bi-directional clipboard, drag-and-drop functionality).
- Create two virtual machines:
  - **Windows Server 2019 VM**: Used as the Domain Controller.
  - **Windows 10 VM**: Acts as a client machine for connecting to the domain.

**Ref 1: VirtualBox Installation and VM Setup**  
![VirtualBox Installation](imgsrc)  
_Explanation_: Screenshot showing the VirtualBox setup and the creation of two VMs: Windows Server 2019 and Windows 10.

### Step 2: Configuring the Domain Controller
- Set a static IP address for the internal network adapter on the Windows Server 2019 VM.
- Install **Active Directory Domain Services (AD DS)** and promote the server to a Domain Controller (DC) with the domain name **mydomain.com**.
- Create a domain admin account for managing the domain.

**Ref 2: AD DS Installation and Static IP Configuration**  
![Domain Controller Setup](imgsrc)  
_Explanation_: Screenshot showing the Active Directory configuration, including static IP setup and domain promotion.

### Step 3: Setting Up NAT and DHCP on the Domain Controller
- Install **Routing and Remote Access Service (RRAS)** to enable **Network Address Translation (NAT)** on the Domain Controller.
- Install and configure the **DHCP role** to automatically assign IP addresses to the Windows 10 client on the internal network.

**Ref 3: NAT and DHCP Setup**  
![NAT and DHCP Configuration](imgsrc)  
_Explanation_: Screenshot showing the RRAS configuration for NAT and the DHCP setup for the internal network.

### Step 4: Automating User Creation with PowerShell
- Use a PowerShell script to create **1,000 users** in Active Directory.
- The script reads names from a text file and assigns each user a default password and organizes them into **Organizational Units (OUs)**.

**Ref 4: PowerShell User Creation**  
![PowerShell User Script](imgsrc)  
_Explanation_: Screenshot showing the PowerShell script execution and user creation in Active Directory.

### Step 5: Setting Up the Windows 10 Client
- Install and configure the **Windows 10 VM** with an internal network adapter so it can communicate with the Domain Controller.
- Join the Windows 10 machine to the **mydomain.com** domain.
- Log in using one of the newly created domain user accounts from the PowerShell script.

**Ref 5: Joining Windows 10 to the Domain**  
![Windows 10 Domain Join](imgsrc)  
_Explanation_: Screenshot showing the Windows 10 machine being successfully joined to the domain.

### Step 6: Verifying Connectivity
- Ensure that the **Windows 10 client** receives an IP address from the Domain Controller via DHCP.
- Verify internet connectivity by pinging external websites through the Domain Controller’s NAT setup.

**Ref 6: Verifying Connectivity**  
![Connectivity Test](imgsrc)  
_Explanation_: Screenshot showing successful internet connectivity and IP assignment on the Windows 10 client machine.

## Challenges and Solutions
- **NAT Configuration Issues**: Configuring the correct NAT settings for internet access took some trial and error, but enabling RRAS and setting up the correct internal/external networks resolved the problem.
- **PowerShell Automation**: Initially, the PowerShell script encountered errors due to incorrect file formatting. This was fixed by ensuring the text file was properly structured for user creation.

## Results
- Successfully created an Active Directory environment with a Domain Controller running on Windows Server 2019 and a Windows 10 client machine joined to the domain.
- Automated the creation of **1,000 users** using PowerShell.
- Verified internet connectivity and internal network communication between the Domain Controller and client.

## Learning Outcomes
- Developed skills in configuring and managing an Active Directory environment.
- Gained experience in automating user creation and managing large user environments with PowerShell.
- Improved understanding of network services (NAT, DHCP) and their integration in a virtual lab environment.

## Next Steps
- Experiment with **Group Policy** for managing domain policies and user permissions.
- Implement additional security measures, such as **multi-factor authentication (MFA)** for domain users.
- Expand the lab environment with more clients and services, such as file sharing and group policy objects (GPOs).
