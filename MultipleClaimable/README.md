The files in this folder are meant to create multiple claimable VMs in a lab using the CLI script to execute the template. The parameters include the number of machines and the username/password combination.

To deploy the multi-vm template using the supplied parameter files first edit the parameters to match your desired settings, then copy both into a local directory and execute the following command after logging in (replace the name of the resource group with the name of the resource group that contains your lab):

`az group deployment create -g lgLabWithLoadbalancerAndNAT --parameters @MultiVM.params.json --template-file  MultiVMTemplate.json`

*_Note_*: The above command is using Azure CLI 2.0 version 0.1.0b11 available [here](https://github.com/Azure/azure-cli)

There are two version available, the first version uses a marketplace image as the base image to create the lab virtual machines. The second version uses a custom image that has been added to the DevTest lab. The first version uses the files `MultiVMTemplate.json` and `MultiVMTemplate.params.json`. The second version uses the files `MultiVMCustomImageTemplate.json` and `MultiVMCustomImage.params.json`.

_Ensure that the subnet that is used has the `Enable Shared Public IP` setting enabled._ This is found by selecting `Configuration` in the lab blade in the Azure portal and then selecting `Virtual Networks` and then the subnet that you will be using for your deployment. At the time of this writing some of these capabilities are under development and may not appear in your version of the Azure portal.