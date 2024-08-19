
Click the Below to deploy to Azure 
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdoyinr6%2Fcybrush%2Fmain%2FDeploymentTemplate%2FDeploy-Remediate-User.json)

 This steps provide clear and direct guide for users.
### Setting Up App Registration and Retrieving Credentials

#### Step 1: Register an Application in Azure AD
1. **Navigate to Azure AD**: Go to the Azure portal and select **Azure Active Directory**.
2. **App Registrations**: In the sidebar, click **App registrations** and then **New registration**.
3. **Register the App**: Provide a name, choose the supported account types, and click **Register**.


#### Step 2: Retrieve the Client ID, Tenant ID, and Create Client Secret
1. **Overview Page**: Copy the **Application (client) ID** and **Directory (tenant) ID** from the Overview page.

2. **Certificates & Secrets**: Go to **Certificates & secrets**, create a new client secret, and copy the **Value** (Client Secret). Client ID is on the overview page.


#### Step 3: Assign Required API Permissions
1. **API Permissions**:
   - Click **Add a permission** and select **Microsoft Graph**.
   - Add **Application permissions**:
     - `Directory.ReadWrite.All`
     - `User.EnableDisableAccount.All`
     - `User.ReadWrite.All`
   - **Grant Admin Consent**.

### Deployment Form Overview for Logic App in Azure Portal

**When deploying the Logic App template, you need to provide the following information:**

1. **Subscription and Resource Group**:
   - Select your Azure subscription and specify a resource group.

2. **Region and Logic App Name**:
   - Choose the deployment region (e.g., "UK South") and provide a name for your Logic App.

3. **Azure Sentinel Connection Info**:
   - **Connection ID**: Format: `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Web/connections/{connectionName}`. Find this in **API connections**.
   - **Connection Name**: Enter a name like “Azure-sentinel-1”.

### Summary of Required Parameters:

- **Tenant_ID**: The Azure AD Tenant ID.
- **client_id**: The Application (client) ID.
- **client_secret**: The client secret value.
- **azureSentinelConnectionId**: The formatted Connection ID.
- **azureSentinelConnectionName**: The connection name.

