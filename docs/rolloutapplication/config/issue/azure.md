# Azure Integration Setup

This page provides step-by-step guidance to configure Azure  as your Issue Management Provider and connect it seamlessly with your development workflow.  

## Configuration Fields for Jira

The table below outlines the required configuration fields for integrating Azure with your system.

| Field                 | Value / Description                            |
| --------------------- | ---------------------------------------------- |
| Provider              | Jira                                           |
| Provider Version      | V5                            |
| Base URI              | ` https://dev.azure.com/your-organization` |
| Project Category      | `fixVersion`                                   |
| Username              | Azure user account                              |
| Personal Access Token | Generated from Atlassian                       |
| Authentication Type   | oAuthBasics                                    |

These values will be entered in the Issue Management Provider settings form as shown in the example.

   <div style="text-align: left;">
      <img src="./assets/91.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

## How to Generate Azure PAT:

Follow the below mentioned steps to generate Azure PAT:

1. Log in to Azure DevOps
2. Click profile 
4. Navigate to Personal Access Tokens
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