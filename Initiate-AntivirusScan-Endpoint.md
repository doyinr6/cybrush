**Playbook Overview:** Initiating Full Disk Antivirus Scan on Endpoints
This playbook automatically triggers a full disk antivirus scan on all endpoints associated with an incident in Azure Sentinel. The scan helps to detect and mitigate potential threats by thoroughly checking the entire disk for malicious files and activities. This action is crucial for incident response, ensuring that any threats on the affected endpoints are identified and dealt with promptly.
Click the Below to deploy to Azure.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdoyinr6%2Fcybrush%2Fmain%2FDeploymentTemplate%2FDeploy-AntivirusScan-Endpoint.json)

**Deployment Requirements:**
The screen highlights the deployment form for a Logic App in the Azure Portal. Key information needed includes:

Subscription and Resource Group: Select the Azure subscription under which the Logic App will be deployed and specify or create a resource group to organize related resources.
Region and Logic App Name: Choose the deployment region (e.g., UK South) where the Logic App will be hosted, and provide a meaningful name for your Logic App, such as "Initiate-AntivirusScan-Endpoint."
Azure Sentinel Connection Info:
Connection ID: Provide the Connection ID to link the Logic App with Azure Sentinel. Use the format:
bash
Copy code
/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/connections/{connectionName}
Connection Name: Enter a descriptive name for the connection, like “Azure-sentinel-connection.”
To find this information, navigate to API connections in the Azure portal, or create a new connection if necessary.
