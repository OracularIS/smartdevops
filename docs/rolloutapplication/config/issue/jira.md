# Jira Integration Setup

This page provides step-by-step guidance to configure Jira as your Issue Management Provider and connect it seamlessly with your development workflow.  

## Configuration Fields for Jira

The table below outlines the required configuration fields for integrating Jira with your system.

<center>

| Field                 | Value                          |
| --------------------- | ---------------------------------------------- |
| Provider              | Jira                                           |
| Provider Version      | V2 (for Jira Cloud)                            |
| Base URI             | `https://your-organization-jira.atlassian.net` |
| Project Category      | `fixVersion`                                   |
| Username              | Jira user account                              |
| Personal Access Token | Generated from Atlassian                       |
| Authentication Type   | oAuthBasics                                    |

</center>

These values will be entered in the Issue Management Provider settings form as shown in the example.

   <div style="text-align: left;">
      <img src="./assets/90.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
  
> 💡 **Tip:** Use the **suggestion button** to see recommended inputs and sample values for the field.  


## How to Generate JIRA PAT:
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


---
<br>