# justtesting

There are 3 ARM Templates uploaded to this repository, all with small tweaks from the original.  The core of the template is to deploy multiple VMs to Azure with only the necessary parameters (NIC, Public IP, Storage Account, VM), in addition to the OMS extension.  

DeployMultipleVMs_WithOMSExtension - This template deploys x VMs to Azure based on multiple parameters that you populate during the execution of  New-AzureRmResourceGroupDeployment (PowerShell) or azure group deployment create (Azure CLI).

DeployMultipleVMsToExistingVNET_WithOMSExtension - Same logic but adds code to deploy VMs to an existing VNET in another resource group rather than creating a new VNET or being forced to deploy to a VNET in the specified resource group.
