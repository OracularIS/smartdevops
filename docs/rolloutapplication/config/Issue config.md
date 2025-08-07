# Issue Management Provider 
 
The Issue Management Provider feature enables smooth integration with popular tools like Jira and Azure DevOps.

By setting up basic details such as the base URI, authentication, and project identifiers you can sync your development workflow in real time with your issue tracking system.

Whether you are using Jira or Azure DevOps, this integration improves collaboration, boosts visibility, and ensures clear traceability throughout the software development lifecycle.
 
## Configuring Issue Management Providers

To configure issue tracking integration:

- Go to Settings in the sidebar.

- Open the Issue Management Provider screen.
 
  <div style="text-align: left;">
      <img src="./assets/c1.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

The following table outlines the configuration values required for integrating Jira and Azure DevOps with the Issue Management Provider system:

| Configuration Field              | Jira                                      | Azure DevOps                           |
|----------------------------------|---------------------------------------------------------------|------------------------------------------------------------|
| **Provider**                    | `Jira`                            | `Azure`                        |
| **Provider Version**            | ` V2` (for JIRA Cloud)     | ` V5`                   |
| **Base URI**                    | ` https://your-organization-jira.atlassian.net` | ` https://dev.azure.com/your-organization` |
| **Project Category**            | `fixVersion`              | `fixVersion`                                              |
| **Username**                    | `Jira user account`               | `Azure DevOps account`         |
| **Personal Access Token (PAT)** | `Generated from Atlassian`        | `PAT from Azure DevOps`        |
| **Authentication Type**         | ` oAuthBasics`                    | `OAUTHBASIC`                  |


### How to Generate JIRA PAT:
Follow the below mentioned steps to generate JIRA PAT:
1. Log in to your Jira account
2. Go to: https://id.atlassian.com/manage-profile/security/api-tokens
3. Click Create API Token.

    <div style="text-align: left;">
      <img src="./assets/token1.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

4. Now enter name and generate the token.
    <div style="text-align: left;">
      <img src="./assets/token2.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
4. Copy & paste into the configuration field

### How to Generate Azure PAT:

Follow the below mentioned steps to generate Azure PAT:

1.  Log in to Azure DevOps
2. Click profile → Personal Access Tokens
3. Create new token with scopes (Code, Work Items, Projects)
4. Copy & paste into configuration

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