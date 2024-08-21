**Playbook Overview:**
Investigating Indicators of Compromise with OTX AlienVault

This playbook investigates file hashes, URLs, and IP addresses for threat intelligence using OTX AlienVault. It enriches Azure Sentinel incidents with a table of 2-5 descriptions related to the identified entities and their TI information.

**Click Here to Deploy** :
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdoyinr6%2Fcybrush%2Fmain%2FDeploymentTemplate%2FDeploy-Alienvault-OTX.json)

**Deployment Requirements:**

<img width="855" alt="image" src="https://github.com/user-attachments/assets/3b28475a-07ce-43f7-9e32-e5ce69fe05df">

The screen highlights the deployment form for a Logic App in the Azure Portal. Key information needed includes:

- Subscription and Resource Group: Select your Azure subscription and specify a resource group.
- Region and Logic App Name: Choose the deployment region (e.g., UK South) and name your Logic App.
- Azure Sentinel Connection Info: Provide the Connection ID and Connection Name in the format:
    /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/connections/{connectionName}
    Find this under API connections or create a new one.
- API Keys: Enter your OTX AlienVault API key.
