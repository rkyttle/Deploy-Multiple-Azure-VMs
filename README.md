The core of this template is to deploy multiple VMs to Azure with only the necessary parameters (NIC, Public IP, Storage Account, VM), in addition to the OMS extension.  This template deploys x VMs to Azure based on multiple parameters that you populate during the execution of New-AzureRmResourceGroupDeployment (PowerShell) or azure group deployment create (Azure CLI).  The VMs are added to the specified VNET rather than being hardcoded to the resource group specified in the New-AzureRmResourceGroupDeployment parameters.

To deploy the template using PowerShell: 

Login-AzureRmAccount 
Select-AzureRmSubscription -SubscriptionName '<subscription name>'

$ResourceGroupName='<resource group name>' #This is the resource group where the VMs and other resources specified will be deployed
$TemplateFilePath='<local path to template>'
$TemplateUri='https://raw.githubusercontent.com/shawntierney/Deploy-Multiple-Azure-VMs-with-OMS-Extension/master/DeployMultipleVMs_OMSExtension_ExistingVNET_NoDefault.json'

New-AzureRmResourceGroupDeployment -Name TestDeployment -ResourceGroupName $ResourceGroupName -TemplateUri $TemplateUri 

Use the following link for help deploying templates: https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-template-deploy


