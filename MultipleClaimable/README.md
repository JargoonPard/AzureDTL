The files in this folder are meant to create multiple claimable VMs in a lab using the CLI script to execute the template. The parameters include the number of machines and the username/password combination.

To deploy the multi-vm template using the supplied parameter files first edit the parameters to match your desired settings, then copy both into a local directory and execute the following command after logging in (replace the name of the resource group with the name of the resource group that contains your lab):

`az group deployment create -g lgLabWithLoadbalancerAndNAT -n testmulti1 --parameters '@MultiVM.params.json' --template-file  MultiVMTemplate.json`

Note: The above command is using Azure CLI 2.0 version 0.1.0b11 available [here](https://github.com/Azure/azure-cli)