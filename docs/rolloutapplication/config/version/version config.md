# Version Control Provider
 
 The Version Control System (VCS) integration enables the application to connect with platforms like **Bitbucket** and **Azure Repos**, allowing teams to manage and track source code changes efficiently. 
 
 By configuring essential parameters such as repository URIs, authentication tokens, API versions, and default branches, users can automate version tracking and streamline deployment workflows.
 
With support for multi-file paths, custom workspaces, and default branch targeting, the VCS integration is designed to support modern DevOps practices and continuous deployment pipelines.

## Configuring Issue Management Providers
To configure version control integration follow the steps:
 
- Click on Settings from the sidebar.
- Navigate to the Version Control Provider screen.

    <div style="text-align: left;">
      <img src="./assets/92.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

- Select your provider like git or svn.

- Follow the provider-specific setup guide:
  - [Configure Bitbucket Integration](/rolloutapplication/config/version/bitbucket.md)
  - [Configure Azure Integration](/rolloutapplication/config/version/azureversion.md)



---
<br>