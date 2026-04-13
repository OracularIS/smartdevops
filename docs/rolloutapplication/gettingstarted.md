# Getting Started

Learn how to access the Rollout Application and start using its features to efficiently manage rollouts and streamline your workflow.

## Prerequisites

Before getting started with Rollout Application, ensure the following requirement is met:

- **Extensibility Compliance Mode**
 
  For new environments, the Extensibility Compliance Mode must be **disabled**.

  <div style="text-align: left;">
    <img src="./assets/pre1.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

  This setting ensures that required environment variables are publicly accessible, which is necessary for proper system functionality and integrations.

- **Registry**

  Before using Rollout Application, ensure the required registry paths are properly configured.
  - **Set GITSBXDIR Environment Path**:
  
       The GITSBXDIR must be configured in the **Environment section** of the registry file.

       In the registry file, it should appear as:

       ```ini
       [ENVIRONMENT]
       GITSBXDIR=E:/../VAL_WM
       ```
    Ensure that the path is correctly set according to your environment setup.

  - **Security Configuration**

    In the **SECURITY** section of the registry, update the `safe-file-directories` parameter to include both **GITSBXDIR** and **LESDIR**. 


       <div style="text-align: left;">
       <img src="./assets/reg2.jpg"
              alt="undirectedmenu"
              style="height: 200px; margin: auto; display: block; cursor: zoom-in;
                     border: 2px solid #000000; border-radius: 4px;"
              onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
              ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
       </div>

       This step is required to allow proper access and ensure the application can securely read the necessary environment paths.

## Logging In

To begin, open the Rollout Application in your browser:

**URL :** [https://rolloutdemo.smart-is.com
 ](https://rolloutdemo.smart-is.com/)

You can log in using any of the following methods:

**Google**

Click **"Login with Google"** and select your Google account to proceed.

 <div style="text-align: left;">
    <img src="./assets/image37.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


**Microsoft**

Click **"Login with Microsoft"** and authenticate using your Microsoft account credentials.

<div style="text-align: left;">
     <img src="./assets/image38.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

**Username and Password**

1. Enter your registered **Username** and **Password**.
2. Click the **"Login"** button to continue.

<div style="text-align: left;">
     <img src="./assets/image39.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


After a successful login, you will be redirected to the **Application Dashboard**, which serves as the central hub for all features and tools in the Rollout App.

## Application Overview

Get familiar with the core areas of the Rollout Application to navigate and manage your work with ease.

<div style="text-align: left;">
     <img src="./assets/dashboard.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

##  Dashboard

View a visual summary of rollout data through bar charts, line graphs, and pie charts, including insights on bugs, affected files, activities, and projects.

## Projects 

Organize and manage your rollout projects in one place, with options to create both individual and accumulative rollouts.

For detailed information, click [here](/rolloutapplication/overview.md) to explore the Projects page

## Utilities 
Access essential tools to track affected files, review object change history, monitor webhook logs, and generate rollouts, all in one place.

For detailed information, click [here](/rolloutapplication/logs.md) to explore the Utilities page. 


## Configuration 

The Rollout Application supports a variety of configurable settings to adapt to different organizational needs and deployment environments. 

These configurations include issue management provider integration (e.g., Jira, Azure DevOps), version control system setup (e.g., Git with Bitbucket or Azure), rollout package behavior, system preferences, and authentication methods.
 
For detailed information, click [here](/rolloutapplication/config/configuration.md) to explore configuration page.

---

<br><br>