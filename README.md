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

### Load Balancer Setup Steps:

1. **Create Load Balancer (Public)**
   - **Resource Group:** loadbalancer-rg
   - **Virtual Network:** vnet

     ![image](https://github.com/Mouhamed-dridi/azure-load-balancer-public/assets/53900924/0f7dbcaf-4119-4de5-9988-ecd2917f8819)


2. **Create Public IP**
- Create a new public IP for the load balancer.
- 
![image](https://github.com/Mouhamed-dridi/azure-load-balancer-public/assets/53900924/2915727e-bad1-49e4-b528-b74b5257e69f)



3. **Configure VMs as Backend Pool**
   - Associate the VMs as backend targets for the load balancer.
![image](https://github.com/Mouhamed-dridi/azure-load-balancer-public/assets/53900924/17bf4f9a-e741-4ceb-9edb-d8f33a854db2)




4. **Set Up Health Check**
   - Define health probes to monitor the health of the backend VMs.
![image](https://github.com/Mouhamed-dridi/azure-load-balancer-public/assets/53900924/8e93ec64-e912-4579-b1af-d8bebf69d61e)
   


6. **Create Load Balancer Rules**
   - Configure load balancing rules to distribute incoming traffic among the backend VMs.
![image](https://github.com/Mouhamed-dridi/azure-load-balancer-public/assets/53900924/0a0f69c6-070c-4b8f-8fe5-c32a4258dc37)



7.  **Befor test**
 - its recommande to allow the http and https
   ![image](https://github.com/Mouhamed-dridi/azure-load-balancer-public/assets/53900924/e4434408-955f-41a9-a3ff-0d2050fe2fdf)


   8. **Befor test**
      - for testing use the public ip of the loadbalincer just put ip bulic in brwoser and can use also private browser
        ![image](https://github.com/Mouhamed-dridi/azure-load-balancer-public/assets/53900924/4422fc8c-9b82-4bcd-a26d-af56770ecc45)
