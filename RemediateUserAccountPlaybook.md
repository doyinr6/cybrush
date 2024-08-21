**Playbook Overview: Remediating User Accounts in Response to Incidents**


The "Remediate User Account" playbook automatically addresses incidents involving potentially compromised user accounts by resetting the user's password, disabling the account to prevent further unauthorized access, and enforcing Multi-Factor Authentication (MFA) upon the next sign-in. This ensures that the affected accounts are swiftly and securely remediated, aligning with best practices for incident response in Azure Sentinel.


Click the Below to deploy to Azure.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdoyinr6%2Fcybrush%2Fmain%2FDeploymentTemplate%2FDeploy-Remediate-User.json)

<img width="855" alt="image" src="https://github.com/user-attachments/assets/d2dbb14f-e506-49e0-a444-2a98a5f7c52b">


 These steps provide clear and direct guide for users.
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
2. **Admin Permissions**:
 - Assign the User amdinsitrator role or global admin role depending on the level of access you want to the application.
   
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

