# Rollout Actions
Rollout actions allow you to efficiently manage the lifecycle of your rollouts.
 You can create new rollouts to initiate changes, remove outdated or unnecessary ones, regenerate rollouts when updates are required, and access detailed information to track and review each rollout with ease.

## Project List

From the Dashboard, navigate to the **Projects** screen using the main sidebar.

 <div style="text-align: left;">
    <img src="./assets/image41.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


This screen provides an overview of ongoing rollout activities and acts as the starting point for initiating new rollouts.

 <div style="text-align: left;">
    <img src="./assets/image42.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

---

## Steps to Create a New Rollout

The latest rollout flow uses a guided three-step wizard: **Select project**, **Choose version**, and **Rollout Details**.

1. Open the **Projects** page and click **Create Rollout**.

   You can start from the page-level **Create Rollout** button in the upper-right corner or from the **Create Rollout** action shown on a project row.

 <div style="text-align: left;">
    <img src="./assets/rollout-step-1-open-create-rollout.png"
       alt="Project List page with Create Rollout actions"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. In **Step 1 - Select project**, find the project you want to use.

   Use the **Search by project name...** field to filter the list if needed, review the available projects, and click the required project to continue.

   The page also provides a **Sync projects** action if you need to refresh the project list before making a selection.

 <div style="text-align: left;">
    <img src="./assets/rollout-step-2-select-project.png"
       alt="Create Rollout wizard step 1 for selecting a project"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. In **Step 2 - Choose version**, select the release version for the chosen project.

   The selected project is shown at the top of the step. If needed, click **Change** to go back and choose a different project, then click the required version from the list to continue.

 <div style="text-align: left;">
    <img src="./assets/rollout-step-3-choose-version.png"
       alt="Create Rollout wizard step 2 for choosing a version"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

4. In **Step 3 - Rollout Details**, review the selected **Project** and **Version**, then complete the rollout form.

   Fill in or review the following fields shown in the current UI:

   - **Rollout Name**
   - **Version**
   - **Environment** *(Optional)*
   - **Bug IDs**
   - **Platform**
   - **Tags**
   - **Description**

   If you need to update the selected project or version, use the **Change** link next to that value before creating the rollout.

 <div style="text-align: left;">
    <img src="./assets/rollout-step-4-rollout-details.png"
       alt="Create Rollout wizard step 3 showing rollout details fields"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

5. Click **Create Rollout** to finish creating the rollout, or click **Cancel** to leave the form without saving.

 <div style="text-align: left;">
    <img src="./assets/rollout-step-5-create-rollout-action.png"
       alt="Create Rollout action buttons for submitting or cancelling the rollout"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

### Alternative Flow: Create Rollout from a Project Row

You can also create a rollout directly from a project row without going through the separate **Select project** and **Choose version** steps.

1. On the **Projects** page, find the required project row and click the **Create Rollout** button shown on that row.

   This action uses the project and version already displayed on the selected row.

 <div style="text-align: left;">
    <img src="./assets/rollout-alternate-row-create-button.png"
       alt="Project row Create Rollout button"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. After clicking the row button, the application opens the **Rollout Details** step directly.

   The wizard skips the first two selection screens because the row already identifies the **Project** and **Version** to use. In this shortcut flow:

   - The **Project** is preselected from the row you clicked.
   - The **Version** is preselected from the row you clicked.
   - The form opens on **Step 3 - Rollout Details**.
   - The rollout naming pattern and rollout version value are generated automatically.

 <div style="text-align: left;">
    <img src="./assets/rollout-alternate-row-rollout-details.png"
       alt="Rollout Details page opened directly from the project row shortcut"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. Review the prefilled values, then complete the remaining rollout fields as needed.

   In this screen, confirm the selected project and version, then update or fill in the remaining fields such as:

   - **Environment** *(Optional)*
   - **Bug IDs**
   - **Platform**
   - **Tags**
   - **Description**

   If needed, use the **Change** link beside **Project** or **Version** to go back and adjust the selection.

4. Click **Create Rollout** to create the rollout, or click **Cancel** to leave the form without saving.

<!--

1. Select the required project from the **Select Project** dropdown.

 <div style="text-align: left;">
    <img src="./assets/image43.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


2. Choose the appropriate version from the **Version** dropdown.

    <div style="text-align: left;">
    <img src="./assets/image44.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. Click the **Create Rollout** button to proceed.

    <div style="text-align: left;">
    <img src="./assets/image45.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


After clicking Create Rollout, you’ll be redirected to the Create Rollout page. Follow the steps below to complete the process:

4. On the Create Rollout page, choose the platform by selecting either Windows or Linux.

<div style="text-align: left;">
<img src="./assets/image46.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

5. From the **BugList** dropdown, select one or more relevant bug IDs to associate with the rollout.

    <div style="text-align: left;">
    <img src="./assets/image47.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

6. Enter a brief description in the **Description** text box.

   <div style="text-align: left;">
    <img src="./assets/image48.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

7. Finally, click the Create button to complete the rollout setup.

8. Once the rollout is created, a **success message** will appear on the screen. You can then download the rollout by clicking the text link that says

     'You can download it from here.' 


   <div style="text-align: left;">
    <img src="./assets/image49.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
    

### Alternative Flow
You can also create a rollout directly from the Project List without using the dropdowns.

To do this:

1. Select a row from the existing list of projects and versions.

2. Once selected, the top toolbar will display two options: New and Accumulative.

    **New Rollout** creates a rollout based on the current selection.

    **Accumulative Rollout** gathers all issues previously used to create rollouts for the selected project and combines them into a single rollout.

    <div style="text-align: left;">
    <img src="./assets/image50.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
    
3. Click either New or Accumulative, depending on the type of rollout you want to create.

4. After clicking, you will be redirected to the [Create Rollout](#steps-to-create-a-new-rollout) page where you can complete the rollout setup.
-->

---

## View Existing Rollouts

To view existing rollouts for a project:

1. On the **Projects** page, click the required project row.

   You can click the row directly to open the rollout history for that project and version.

    <div style="text-align: left;">
    <img src="./assets/rollout-list-open-from-project-row.png"
       alt="Project List row used to open the Rollout List page"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. The **Rollout List** page opens and displays the rollouts associated with the selected project and version.

   The page header shows the selected **Project** and **Version**, and the rollout table lists the available rollout records for that selection.

    <div style="text-align: left;">
    <img src="./assets/rollout-list-page-from-project-row.png"
       alt="Rollout List page opened from the selected project row"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

---

## Recreate Rollout

Recreating a rollout allows you to start from an existing rollout entry directly from the **Rollout List** page.

To recreate a rollout:

1. In the **Rollout List** page, select the desired rollout using the checkbox on the left side of the row.

   After a rollout is selected, the top action bar becomes available and shows options including **Recreate** and **Delete rollout**.

    <div style="text-align: left;">
    <img src="./assets/rollout-select-row-for-actions.png"
       alt="Selected rollout row with Recreate and Delete rollout actions visible"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. Click **Recreate** from the top action bar.

   The system opens the rollout form for the selected rollout so you can review the existing details, make changes if needed, and create the rollout again.

    <div style="text-align: left;">
    <img src="./assets/rollout-select-row-for-actions.png"
       alt="Top action bar showing the Recreate button for the selected rollout"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. Review the rollout details, update any required fields, and click **Create Rollout** to finish recreating the rollout.

<!--

Recreating a rollout allows you to generate a new version of an existing rollout. The system automatically increases the minor version in the rollout name to distinguish it from the original.

To recreate a rollout:

1. From the **# of Rollouts** column in the Project List, click on the number next to the desired project.
    <div style="text-align: left;">
    <img src="./assets/image51.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. In the list of existing rollouts, select the rollout you wish to recreate.
    <div style="text-align: left;">
    <img src="./assets/image53.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. Once selected, a top toolbar will appear with two options: **Delete** and **Recreate**.

   - **Delete**: Permanently deletes the selected rollout.  
     ⚠️ *This action is irreversible. Use with caution.*
   
   - **Recreate**: Opens the **Create Rollout** screen, allowing you to revise and recreate the rollout.

    <div style="text-align: left;">
    <img src="./assets/image54.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

4. Update the required fields as needed.

    <div style="text-align: left;">
    <img src="./assets/image55.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

5. Click the **Create Rollout** button.

    <div style="text-align: left;">
    <img src="./assets/image56.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

After successful creation, a confirmation message will appear, indicating that the rollout has been recreated.

<div style="text-align: left;">
    <img src="./assets/image49.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
-->

---

## Delete Rollout

To delete an existing rollout:

1. In the **Rollout List** page, select the rollout you want to delete using the checkbox on the left side of the row.

   After you select a rollout, the top action bar displays **Delete rollout** and **Recreate**.

    <div style="text-align: left;">
    <img src="./assets/rollout-select-row-for-actions.png"
       alt="Selected rollout row with actions available in the top bar"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. Click the **Delete rollout** button in the top action bar.

    <div style="text-align: left;">
    <img src="./assets/rollout-delete-button.png"
       alt="Delete rollout button in the top action bar"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. A confirmation dialog appears. Click **Delete rollout** to confirm the deletion, or click **Cancel** to stop the action.

    <div style="text-align: left;">
    <img src="./assets/rollout-delete-confirmation-modal.png"
       alt="Delete rollout confirmation dialog"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

   This action permanently removes the selected rollout and cannot be undone.

<!--

To delete an existing rollout:

1. From the **# of Rollouts** column in the Project List, click on the number next to the desired project.

    <div style="text-align: left;">
    <img src="./assets/image51.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. In the list of existing rollouts, select the rollout you want to delete. Once selected a top toolbar will appear with two options: **Delete** and **Recreate**.

    <div style="text-align: left;">
    <img src="./assets/image57.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


3. Click the **Delete** button to permanently remove the selected rollout.

   ⚠️ **Warning:** This action cannot be undone. Use caution when deleting rollouts.

   
    <div style="text-align: left;">
    <img src="./assets/image58.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

4. A confirmation dialog will appear. Click **YES** to confirm the deletion.

    <div style="text-align: left;">
    <img src="./assets/image59.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

5. After confirmation, the rollout will be removed, and a success message will be displayed on the screen.
    <div style="text-align: left;">
    <img src="./assets/image60.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>
-->

---
## Download Rollout

You can download rollout files either by selecting an entire rollout or by downloading files specific to individual bugs within a rollout.

### Download Full Rollout File

1. In the **Rollout List** page, locate the rollout you want to download.

2. Use the **TAR** button in the **Download** column to download the rollout in TAR format.

    <div style="text-align: left;">
    <img src="./assets/rollout-download-button.png"
       alt="TAR download button in the Download column"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. If you need a ZIP file instead, click the dropdown arrow on the same button and choose **Download ZIP**.

    <div style="text-align: left;">
    <img src="./assets/rollout-download-zip-option.png"
       alt="Download ZIP option opened from the Download menu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

The rollout file will begin downloading in the format you selected.

<!--

1. From the **# of Rollouts** column in the Project List, click on the rollout count next to the relevant project.

    <div style="text-align: left;">
    <img src="./assets/image51.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. In the list of rollouts, locate the required entry.

    <div style="text-align: left;">
    <img src="./assets/image61.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. Click the **Zip/Tar** icon next to the rollout.

    <div style="text-align: left;">
    <img src="./assets/image62.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

The rollout file will begin downloading in `.zip` or `.tar` format, depending on system configuration.
-->

---

### Download Rollout for a Specific Bug

You can also download a rollout package tied to a specific bug included in the rollout:

1. In the **Rollout List** page, click the bug count shown in the **Bugs** column for the rollout you want to inspect.

    <div style="text-align: left;">
    <img src="./assets/rollout-bugs-count-link.png"
       alt="Bug count in the Bugs column"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';"/>
      </div>

2. The **Rollout Bugs** dialog opens and shows the bugs associated with that rollout.

    <div style="text-align: left;">
    <img src="./assets/rollout-bugs-modal.png"
       alt="Rollout Bugs dialog showing bug-level download options"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';"/>
      </div>

3. To download the package for a specific bug, use the **TAR** button on that bug row.

   If needed, use the dropdown on the same button to choose another available download option.

4. To download the rollout package for all bugs shown in the dialog, use **Download Rollout TAR** at the top of the modal.

The selected file will begin downloading in the chosen format.

<!--

You can also download a rollout package tied to a specific bug included in the rollout:

1. From the rollout details screen, locate the specific bug entry from **# of Rollouts**

    <div style="text-align: left;">
    <img src="./assets/image63.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


2. Choose your desired platform using the toggle switch:
   - Move the toggle to **Windows** for a Windows-compatible file.
   - Move it to **Linux** for a Linux-compatible file.

       <div style="text-align: left;">
        <img src="./assets/image64.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

3. Click the **Download** button.
    <div style="text-align: left;">
    <img src="./assets/image65.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>



The file will begin downloading in the appropriate format for the selected platform.
-->

---

<br><br>
