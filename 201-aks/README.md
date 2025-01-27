# Azure Container Service (AKS)

<IMG SRC="https://azurequickstartsservice.blob.core.windows.net/badges/201-aks/PublicLastTestDate.svg" />&nbsp;
<IMG SRC="https://azurequickstartsservice.blob.core.windows.net/badges/201-aks/PublicDeployment.svg" />&nbsp;

<IMG SRC="https://azurequickstartsservice.blob.core.windows.net/badges/201-aks/FairfaxLastTestDate.svg" />&nbsp;
<IMG SRC="https://azurequickstartsservice.blob.core.windows.net/badges/201-aks/FairfaxDeployment.svg" />&nbsp;

<IMG SRC="https://azurequickstartsservice.blob.core.windows.net/badges/201-aks/BestPracticeResult.svg" />&nbsp;
<IMG SRC="https://azurequickstartsservice.blob.core.windows.net/badges/201-aks/CredScanResult.svg" />&nbsp;

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F201-aks%2Fazuredeploy.json" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F201-aks%2Fazuredeploy.json" target="_blank">
<img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.png"/>
</a>

This template deploys an **AKS cluster**.

See https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough for a walkthrough.

To use keys stored in keyvault, replace ```"value":""``` with a reference to keyvault in parameters file. For example:

```json
"servicePrincipalClientSecret": {
      "reference": {
        "keyVault": {
          "id": "<specify Resource ID of the Key Vault you are using>"
        },
        "secretName": "<specify name of the secret in the Key Vault to get the service principal password from>"
      }
    }
```

If you are new to **Azure Kubernetes Service (AKS)**, see:

- [Azure BlockChain Services](https://docs.microsoft.com/en-gb/azure/aks/).
- [Template reference](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/aks-allversions)

If you are new to template deployment, see:

[Azure Resource Manager documentation](https://docs.microsoft.com/azure/azure-resource-manager/)

`Tags: Azure4Student, Kubernetes, AKS, Intermediate`
