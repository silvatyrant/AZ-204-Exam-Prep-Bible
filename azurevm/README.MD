# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[Azure VM](https://docs.microsoft.com/en-us/azure/virtual-machines)
---------

### General
**Provisioning**
* [Cloud-init](https://cloudinit.readthedocs.io/) for Linux VM provisioning and Powershell scripts for Windows VM provisioning.
 * Linux VM vs Windows VM.
 * Tiering based on ACUs and disk.
 * Trusted launch VMs:
   * Secure Boot
   * vTPM
   * VBS & HVCI
* **Storage**
  * Standard disks (HDDs) vs. Premium disks (SSDs).
  * Managed (Max capacity is 4TB) vs. Unmanaged (Storage account File storage).
* **VM Extensions**
* Custom script extension for post-provisioning customisation
* Powershell Desired State Configuration (DSC)
* Azure Diagnostics Extension

**Application Deployment**
  **Windows**
Steps to publish a webapp from Visual Studio to IIS on a Azure hosted **Windows** VM:

  1. Assign a static IP address
  2. Assign a DNS name
  3. Add an incoming rule for port 8172 to NSG
  4. Add the Management service role to the server
  5. Check configuration of the Management service in IIS
  6. Install .NET Core Hosting Bundle. This allows .NET Core apps to be hosted in IIS.
  7. Install the Web Deploy tool.

  **Linux**
Steps to publish a webapp from Visual Studio to IIS on a Azure hosted **Linux** VM:
  1. Publish to a folder
  2. Copy folder to server (using a SCP tool like WinSCP)
  3. Install ASP.Net Core SDK 3.1
  4. Install NGINX
  5. Configure NGINX to proxy incoming HTTP requests on port 80 to the ASP.Net Core app in the Kestrel container on port 5000

### Tech Tips
* List available images 
`az vm image list lists images`
* Resizing/horizontal scaling of VMs can cause a reboot.

### High Availability / Scalability
* [Best practices](https://docs.microsoft.com/en-us/azure/architecture/checklist/resiliency-per-service#virtual-machines)
  * No prod workloads on single VM.
  * Specify availability set during provisioning.
  * Each app tier in separate availability sets.
  * Replicate Vms using Azure Site Recovery.
  * Pick correct VM size based on performance requirements (do baselining).
  * Use manage disks for VHDs.
  * Apps on data disks not OS disks.
  * Use Azure Backups.
  * Enable diagnostic logs.
  * Configure [Azure Monitor](../monitor/README.MD)

* **[Availablity sets](https://www.c-sharpcorner.com/article/availability-set-fault-domains-and-update-domains-in-azure-virtual-machie/)** allow for VMs to be grouped in such a way that apps are available during faults (across **Fault Domains**) or maintenance/updates (across **Update Domains**).
* **Fault domains** share power and network devices in a data centre.
* **Update Domains** are Azure-managed grouped sets of resources that can be shutdown for maintenance without impacting application availablity.
* **Scale sets** are sets of VMs which are loadbalanced and can be automatically scaled out/in based on load or schedule (see [limitation](#notable-limits) below).
  
### Notable Limits**
 * Max 1000 in scale sets.
 * Max 20 VMs per region in subscription - Limited can be raised with support ticket.

### Labs 
Source: Exam AZ-204: Developing Solutions for Microsoft Azure - Skills Measured (updated March 26 2021)
```
- provision virtual machines (VMs)
```
 * [Deploy applications to a Windows virtual machine in Azure with the Custom Script Extension](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/tutorial-automate-vm-deployment)

### Related Services
[Azure Resource Manager](../arm/README.MD) | [Azure Storage Account](../storage/README.MD) | [Azure Monitor](../monitor/README.MD)