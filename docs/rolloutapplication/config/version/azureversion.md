# Configure Bitbucket Integration

This page provides step-by-step guidance to configure git as your Version Control Provider.  

## Configuration Fields for Azure

Below are the configuration fields and their descriptions for setting up Azure as your version control provider:  

| Field                         | Value                                                                                |
| ----------------------------- | ----------------------------------------------------------------------------------------------------- |
| Provider      |  git                             |
| Provider Type | Azure                                     |
| Version Control URI           | https://dev.azure.com/your-organization         |
| API Version   | v5_1  |
| Username      | Azure account user name                                                         |
| Password     | Personal Access Token (PAT)|
| Workspace         | Workspace system.                                            |
| File Version                 | Latest                                      |
| Default Branch              | your branch e.g, main                                         |
| File Path     | your file path                   |



These values will be entered in the Version Control Provider settings form as shown in the example.

   <div style="text-align: left;">
      <img src="./assets/94.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

## How to Generate Azure DevOps PAT:

Follow the below mentioned steps to generate Azure DevOps PAT:

1. Navigate of your Azuew Profile.
2. Go to Personal Access Tokens and select New Token

   <div style="text-align: left;">
      <img src="./assets/101.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. Select scopes (Code, Project, Work Items)
3. Use the token in `VERSION_CONTROL_PASSWORD`

---
<br>