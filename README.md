# Azure-Load-Balancer-Public
Explore Azure LoadBalancer 🛡️ and optimize your network's efficiency! 💻 Dive into seamless load balancing ⚖️ with Azure's powerful tools. 🚀

### Project Setup Steps:
1. **Create Resource Group for this Project**
2. **Create VNet Network**
3. **Create 2 VMs (Ubuntu) and Install Apache 2 to Test Website**
4. **Create a Public LoadBalancer**


**Create Resource Group for this Project**
```bash
az group create --name loadbalancer-rg --location <location>
```
**Create Virtual Network**
```bash
az network vnet create --name myVNet --resource-group loadbalancer-rg --location westeurope --address-prefixes 10.103.0.0/16
```
**Create Subnet**
```bash
az network vnet subnet create --name subnet-lb --resource-group loadbalancer-rg --vnet-name myVNet --address-prefixes 10.103.0.0/24
```
**Create 2 VMs (Ubuntu) and Install Apache 2 to Test Website**

For this lab, we'll temporarily assign public IPs to the VMs so they can access the internet for tasks like installing Apache or cloning GitHub repositories. After setup, you can remove these public IPs for better security and rely on private IPs for internal communication.

**How connect vms loacly with ssh**
If VMs are created using only private IPs, they can still be accessed locally within the other virtual network. This allows for secure communication without exposure to the public internet

