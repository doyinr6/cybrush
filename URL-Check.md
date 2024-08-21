Playbook Overview: Investigating URLs with VirusTotal and urlscan.io
This playbook focuses on URLs identified in an incident, using VirusTotal and urlscan.io for both static and dynamic analysis. The results generate a URL linking to detailed reports from these sites, providing comprehensive information on the investigated URLs.
Click Button below to deploy.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdoyinr6%2Fcybrush%2Fmain%2FDeploymentTemplate%2FDeploy-URL-Check.json) 


Deployment Requirements:
The screen highlights the deployment form for a Logic App in the Azure Portal. Key information needed includes:

Subscription and Resource Group: Select your Azure subscription and specify a resource group.
Region and Logic App Name: Choose the deployment region (e.g., UK South) and name your Logic App.
Azure Sentinel Connection Info: Provide the Connection ID and Connection Name in the format:
bash
Copy code
/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/connections/{connectionName}
Find this under API connections or create a new one.
API Keys: Enter your API keys for VirusTotal and urlscan.io.
