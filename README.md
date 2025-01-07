# Creating a Virtual Machine on Azure
Learn how to create a basic VM in Azure, configure basic settings, and connect to it.

## Prerequisites
- Microsoft Azure access with a subscription
  
## Steps to create the VM 
1. Create a Resource Group
- In the Azure Portal, search for "Resource Groups" in the search bar. Click "+ Create".
- Enter a Resource Group Name (MyLabRG). Choose a Region (e.g., East US). Click "Review + Create", then "Create".
2. Create a Virtual Machine
- In the search bar, type "Virtual Machines" and select it. Click "+ Create" and choose "Azure Virtual Machine".
- Subscription: Select your subscription. Resource Group: Select the group you created (MyLabRG).
- Virtual Machine Name: Enter a MyLabVM. Region: Choose the same region as your resource group.
- Availability Options: Leave as default. Image: Choose Ubuntu 20.04 LTS (or Windows Server if you prefer). Size: Select Standard_B1s 
- Administrator Account: For Linux: Choose SSH public key or Password. For Windows: Enter a username and password.
- Leave the other options as default and click "Next: Disks
3. Configure Disks
- Use the default options for the OS disk. Click "Next: Networking".
4. Set Up Networking
- Ensure a new virtual network (VNet) and subnet are created automatically. Public IP: Enabled.
- Inbound Port Rules: Select "Allow Selected Ports", then choose RDP (3389) for Windows or SSH (22) for Linux. Click "Review + Create".
5. Review and Create
- Azure will validate your configuration. Click "Create" to deploy the VM. Wait for the deployment to complete (this may take a few minutes).

## Steps to Connect to the Vm
1. Linux VM (SSH):
- Download the private key (if SSH is used) or use the password you set.
- Open a terminal and use: ssh <username>@<public-ip>. Replace <username> and <public-ip> with your actual values from the Azure VM overview.
2. Windows VM (RDP):
- In the Azure Portal, go to your VM, and find the Public IP Address.
- Open "Remote Desktop Connection" on your computer. Enter the public IP, and use the username and password to log in.

## Cleaning UP
- To avoid unnecessary costs, delete the resource group:
- Go to "Resource Groups", select your group (MyLabRG), and click "Delete Resource Group".
