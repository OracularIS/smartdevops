# Version Control Integration
SmartDevOps integrates seamlessly with Git-based version control systems to help you manage and track changes effectively. This section will walk you through how to create a new Git branch, commit your changes, and verify them in Bitbucket.

## GIT

### Create a New Git Branch

  Follow these steps to create a new Git branch for your issue and start working in a structured way.

   1. **Organize your workspace**

      - On your server, navigate to the `gitbx` repository.
      - Create a folder with your **username**.
      - Inside that folder, follow this structure:

        **project-name -> Master folder**

         Replace `project-name` with the actual name of your project (e.g., `bytest`).
    
  2.  **Clone the Repository**
  
      - Clone the repo inside your project directory:
    
        ```bash
        git clone <repository-url>
        ```
      
         Replace repository-url with the actual Git URL provided to you.

  3. **Create a New Branch**

      - Use the pp.sh script to create a new Git branch in your working directory. The branch should have the same name as the Jira issue you're working on.

### Commit Changes in OSSI Issue Assignment

  After completing your development changes, you can now commit changes in Issue Assignment.

  To learn more about Issue Assignment, follow [Issue Assignment](./issueassignment.md)

### Verify the Commit in Bitbucket

  Once you’ve committed your changes, you can verify them directly in Bitbucket:

  1. Navigate to your Bitbucket repository.
  2. Locate the branch you committed to.
  3. Open the branch to confirm that your changes are visible and correctly committed.

  This helps ensure that your version control actions were successful and that your work is properly synced with the repository.


### Create a Pull Request

  To create a pull request follow these steps:

  1. Navigate to the BitBucket screen. 

     <div style="text-align: left;">
     <img src="./assets/image18.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

  2. Click on Create pull request for your branch.

     <div style="text-align: left;">
     <img src="./assets/image19.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
     
     Now click on Create pull request.

     <div style="text-align: left;">
     <img src="./assets/image20.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

  3. Review the code changes shown in the diff view.
  4. Submit the pull request for review.
  5. Approve and merge the pull request into the main branch.
   
     <div style="text-align: left;">
      <img src="./assets/image21.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
     </div>
     

---

<br><br>