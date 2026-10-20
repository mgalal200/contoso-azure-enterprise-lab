# Contoso Egypt | Azure Enterprise Infrastructure Lab

## Project Overview

This project demonstrates hands-on Microsoft Azure administration through a simulated enterprise environment built for practical learning and AZ-104 portfolio development.

The environment hosts a Windows-based web application and demonstrates load balancing, virtual machine scale-out, monitoring, backup and recovery, storage, networking, and access control.

## Architecture

**Region:** East US  
**Resource Group:** `rg-contoso-az104-lab`  
**Operating System:** Windows Server 2022  
**Web Server:** Internet Information Services (IIS)

### Architecture Flow

Internet users  
↓  
Azure Load Balancer (`lb-contoso-web`)  
↓  
Virtual Machine Scale Set (`vmss-contoso-web`)  
↓  
Windows Server 2022 instances running IIS

Supporting services include Azure Virtual Network, Network Security Groups, Azure Monitor, Log Analytics, Azure Backup, Recovery Services vault, Azure Storage, Azure Policy, and Azure role-based access control (RBAC).

## Technologies and Services

- **Compute:** Azure Virtual Machines and Virtual Machine Scale Sets
- **Networking:** Virtual Network, subnet, Network Security Groups, public IP addresses, and Azure Load Balancer
- **Monitoring:** Azure Monitor, Azure Monitor Agent, Data Collection Rules, Log Analytics, and Kusto Query Language (KQL)
- **Backup and Recovery:** Recovery Services vault, VM backup, recovery points, and restored VM validation
- **Storage:** Azure Storage and blob upload/download testing
- **Governance:** Azure Policy and resource tagging
- **Identity and Access:** Managed identity and Azure RBAC
- **Web Hosting:** Internet Information Services (IIS) on Windows Server 2022

## Implementation and Validation

### 1. Web Hosting and Load Balancing
- Deployed a Windows-based IIS website branded as Contoso Egypt.
- Configured an Azure Standard Load Balancer with a backend pool and HTTP health probe.
- Configured a VM Scale Set to serve the website.
- Verified that requests through the load balancer reached different instances.
- Manually scaled the VM Scale Set to three instances and verified that the additional instance served the website.
- Returned the VM Scale Set capacity to two instances.

### 2. Monitoring
- Configured a Log Analytics workspace.
- Configured Azure Monitor Agent and a Data Collection Rule.
- Associated the rule with the virtual machine.
- Verified that monitoring data, including heartbeat and performance records, was available and queried it using KQL.

### 3. Backup and Recovery
- Configured Azure VM backup using a Recovery Services vault.
- Verified backup jobs, backup items, and recovery points.
- Restored a virtual machine without overwriting the original.
- Verified that the restore job completed, the restored VM reached the Running state, and Remote Desktop Protocol (RDP) access worked.

### 4. Storage
- Created a blob container and verified file upload and download operations.

### 5. Governance and Access Control
- Applied a policy requiring resources to carry the `Environment=Lab` tag.
- Troubleshot policy-denied deployments and corrected resource tagging.
- Reviewed role assignments and inherited permissions at resource-group and storage-account scopes.

## Skills Demonstrated

- Azure resource deployment and troubleshooting
- Virtual machine administration
- Load balancing and VM Scale Set management
- Network Security Group configuration and connectivity troubleshooting
- Azure Monitor configuration and KQL queries
- Backup, restore, and recovery validation
- Storage administration
- Azure Policy and resource governance
- Role-based access control and managed identity
- Cost awareness and lab resource cleanup

## Evidence

Screenshots and supporting documentation will be added to demonstrate:

- Website availability through the load balancer
- Responses from different VM Scale Set instances
- Monitoring data and KQL queries
- Successful backup and VM restoration
- Blob storage upload and download
- Policy and access-control configuration

## Notes

This is a personal learning and portfolio lab, not a production deployment. The VM Scale Set scale-out test was performed manually; automatic scaling has not been validated. Resource configurations and costs should be reviewed before using similar designs in production.

## Author

Mohamed Galal  
Microsoft Certified Azure Administrator Associate (AZ-104)
