# Deploy entity enrichment Playbook

In this PLaybook, the aim is to enrich Azure Sentinel incidents with data from entities such as file hashes, URLs, and IPs using Microsoft Azure's Logic Apps.
The setup involves defining a Logic App in Azure, which initiates based on a trigger related to incident entities in Azure Sentinel. This Logic App then fetches and processes data from related entities using APIs from VirusTotal and AbuseIPDB, two services known for their threat intelligence data.
These enriched details are then added as comments to the incidents, thus enhancing the available incident data for analysis. Crucial to the entire process is the careful handling of sensitive data like API keys, ensuring it follows best practices for secure data management.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdoyinr6%2Fcybrush%2Fmain%2Fdeployentity.json)

**Clicking the deploy button will direct you to the deployment tab for setup**.

![image](https://github.com/user-attachments/assets/e11c4462-05fe-4df3-a0f5-0ab6475f1498)

**The screen highlights the deployment form for a Logic App in the Azure Portal. When deploying this template, you need to provide several key pieces of information to ensure the Logic App is configured correctly.
**
- Subscription and Resource Group: Select your Azure subscription and specify a resource group that organizes related Azure resources.
- Region and Logic App Name: Choose the deployment region (e.g., UK South) and name your Logic App.
- Azure Sentinel Connection Info: Provide both the Connection ID and Connection Name to link the Logic App with Azure Sentinel. The Connection ID should follow Format: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/connections/{connectionName}".
- To find in your azure, Check API connections or create one that will be used.  Conneciton Name can look like Azure-sentinel-1.
- API Keys: Enter the necessary API keys for VirusTotal, AbusedIPDB, and Whois. These keys enable your Logic App to fetch threat intelligence data, enhancing the incident data within Azure Sentinel.

**Check out this link for a comprehensive step-by-step guide on how to build this from the ground up.**

https://medium.com/cybrush-entity-enrichment-in-microsoft-sentinel/entity-enrichment-using-logic-apps-virustotal-and-abuseipdb-ac8e2f0b9c3c
