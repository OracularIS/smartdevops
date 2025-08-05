# Version Control Provider Configuration
 
 The Version Control System (VCS) integration enables the application to connect with platforms like **Bitbucket** and **Azure Repos**, allowing teams to manage and track source code changes efficiently. 
 
 By configuring essential parameters such as repository URIs, authentication tokens, API versions, and default branches, users can automate version tracking and streamline deployment workflows.
 
With support for multi-file paths, custom workspaces, and default branch targeting, the VCS integration is designed to support modern DevOps practices and continuous deployment pipelines.

To **configure version control integration** follow the steps:
 
- Click on Settings from the sidebar.
- Navigate to the Version Control Provider screen.

    <div style="text-align: left;">
      <img src="./assets/version.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
 
This screen allows configuration of integration settings for your issue tracking system.

## Configuring Bitbucket as the Version Control Provider
 
1. Select Provider  
   - `VERSION_CONTROL_PROVIDER`: `git`  
   - `VERSION_CONTROL_PROVIDER_TYPE`: `BitBucket`
 
2. Enter Repository URI  
   - `VERSION_CONTROL_URI`: `https://api.bitbucket.org`
 
3. API Version  
   - `VERSION_CONTROL_API_VERSION`: `v2`
 
4. Authentication  
   - `VERSION_CONTROL_USERNAME`: Bitbucket account  
   - `VERSION_CONTROL_PASSWORD`: PAT from Bitbucket
 
5. Workspace (Optional)  
   - `WORKSPACE`: Your Bitbucket workspace name
 
6. File Versioning  
   - `FILE_VERSION`: Leave as `Latest`
 
7. Default Branch  
   - `DEFAULT_BRANCH`: e.g., `main`
 
8. Multi File Path (Optional)  
   - `Multi_File_Path`: e.g., `RPWEB`
 
9. Submit Configuration  
   - Click Submit to save

### How to Generate Bitbucket PAT:

Follow the below mentioned steps to generate Bitbucket PAT:

1. Go to: Account Settings → App Passwords
2. Create new token with all permissions
3. Use this token as your password

## Configuring Azure as the Version Control Provider
 
1. Select Provider  
   - `VERSION_CONTROL_PROVIDER`: `git`  
   - `VERSION_CONTROL_PROVIDER_TYPE`: `Azure`
 
2. Enter Repository URI  
   - `VERSION_CONTROL_URI`: `https://dev.azure.com/your-organization`
 
3. API Version  
   - `VERSION_CONTROL_API_VERSION`: `v5_1`
 
4. Authentication  
   - `VERSION_CONTROL_USERNAME`: Azure DevOps account  
   - `VERSION_CONTROL_PASSWORD`: PAT from Azure DevOps
 
5. Workspace (Optional)  
   - `WORKSPACE`: Your Azure DevOps workspace
 
6. File Versioning  
   - `FILE_VERSION`: Leave as `Latest`
 
7. Default Branch  
   - `DEFAULT_BRANCH`: e.g., `main`
 
8. Multi File Path (Optional)  
   - `Multi_File_Path`: e.g., `RPWEB`
 
9. Submit Configuration  
   - Click Submit to save

### How to Generate Azure DevOps PAT:

Follow the below mentioned steps to generate Azure DevOps PAT:

1. Go to: Profile → Personal Access Tokens → New Token
2. Select scopes (Code, Project, Work Items)
3. Use the token in `VERSION_CONTROL_PASSWORD`

---
<br>