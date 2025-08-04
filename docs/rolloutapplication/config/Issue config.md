# Issue Management Provider Configuration
 
 The Issue Management Provider system in the application allows seamless integration with popular issue tracking tools such as **Jira** and **Azure DevOps**. 
 
By configuring provider settings such as the base URI, authentication credentials, and project identifiers, users can ensure real-time synchronization between their development workflow and the issue tracking platform. 

Whether using Jira’s robust ticketing system or Azure DevOps’ powerful work item tracking, this feature streamlines collaboration, enhances visibility, and ensures traceability across the software development lifecycle.
 

To **configure issue tracking integration** follow the steps:
 
1. Click on Settings from the sidebar.
2. Navigate to the Issue Management Provider Configuration screen.
 
This screen allows configuration of integration settings for your issue tracking system.
 
 
## Configuring JIRA as the Issue Management Provider
 
1. Select Provider  
   - `ISSUE_MANAGEMENT_PROVIDER`: `Jira`
 
2. Select Provider Version  
   - `ISSUE_MANAGEMENT_PROVIDER_VERSION`: `V2` (for JIRA Cloud or latest)
 
3. Enter Base URI  
   - `ISSUE_MANAGEMENT_PROVIDER_BASE_URI`: e.g., `https://smart-is-jira.atlassian.net`
 
4. Project Category  
   - `ISSUE_MANAGEMENT_PROJECT_CATEGORY`: e.g., `fixVersion`
 
5. Username  
   - `ISSUE_MANAGEMENT_USERNAME`: Jira user account
 
6. Personal Access Token  
   - `ISSUE_MANAGEMENT_PASSWORD`: [Generate from Atlassian](https://id.atlassian.com/manage-profile/security/api-tokens)

 
7. Authentication Type  
   - `ISSUE_MANAGEMENT_AUTH_TYPE`: `oAuthBasics`
 
How to Generate JIRA PAT:
 
- Log in to your Jira account
- Go to: https://id.atlassian.com/manage-profile/security/api-tokens
- Click Create API Token, name it, and generate

  <div style="text-align: left;">
      <img src="./assets/token1.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

  
  <div style="text-align: left;">
      <img src="./assets/token2.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
- Copy & paste into the configuration field
 
 
## Configuring Azure as the Issue Management Provider
 
1. Select Provider  
   - `ISSUE_MANAGEMENT_PROVIDER`: `Azure`
 
2. Select Provider Version  
   - `ISSUE_MANAGEMENT_PROVIDER_VERSION`: `V5`
 
3. Enter Base URI  
   - `ISSUE_MANAGEMENT_PROVIDER_BASE_URI`: e.g., `https://dev.azure.com/your-organization`
 
4. Project Category  
   - Leave `ISSUE_MANAGEMENT_PROJECT_CATEGORY` as-is
 
5. Username  
   - `ISSUE_MANAGEMENT_USERNAME`: Azure DevOps account
 
6. Personal Access Token  
   - `ISSUE_MANAGEMENT_PASSWORD`: PAT from Azure DevOps
 
7. Authentication Type  
   - `ISSUE_MANAGEMENT_AUTH_TYPE`: `OAUTHBASIC`
 
How to Generate Azure PAT:
 
- Log in to Azure DevOps
- Click profile → Personal Access Tokens
- Create new token with scopes (Code, Work Items, Projects)
- Copy & paste into configuration

    <div style="text-align: left;">
      <img src="./assets/previewfeature.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

---

<br>