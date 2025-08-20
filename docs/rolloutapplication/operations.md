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

---

## View Existing Rollouts

To view existing rollouts for a project:

1. Select any number from the **# of Rollouts** column next to the desired project.
    <div style="text-align: left;">
    <img src="./assets/image51.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. The list of rollouts associated with that specific project will be displayed on the screen.
    <div style="text-align: left;">
    <img src="./assets/image52.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

---

## Recreate Rollout

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

---

## Delete Rollout

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

---
## Download Rollout

You can download rollout files either by selecting an entire rollout or by downloading files specific to individual bugs within a rollout.

### Download Full Rollout File

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

---

### Download Rollout for a Specific Bug

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

---

<br><br>