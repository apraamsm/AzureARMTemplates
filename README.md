# AzureARMTemplates

To install up to 5 new domain controllers in Azure:
Pre-reqs:
 1.	vNet and a subnet for the new domain controllers must exist in Azure and have correct DNS settings to an existing domain controller
 2.	Create a new site in Active Directory with correct subnet. In the example I have created a site called 'AzureSite' and specified the site in the DSC configuration 'ADDSExistingDomain'
 3. The files in AutomationAccount and Azure Automation DSC folders in this GitHub are needed

* AutomationAccount - ARM Template for creating Automation Account and add credentials, variables and modules (xPendingReboot, xActiveDirectory). Don't forget to save your KEYS (RegistrationKey and RegistrationUrl) from your Automation Account!
* Azure Automation DSC - ARM Template for deploying Iaas VM's with managed disk and static IP address in an existing vNet. Then registers the VM's to Azure Automation DSC with the DSC configuration 'ADDSExistingDomain.localhost'. Choose between 1-5 VM's to deploy.


