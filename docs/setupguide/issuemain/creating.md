# Creating and Closing an Issue

This section explains how to assign a new issue, track related changes, close the issue once complete, and generate a rollout all from the GUI.

## Creating an Issue

1. Navigate to **Configuration → Extensions → OSSI – Issue Assignment** to access the Issue Assignment screen. 

    <div style="text-align: left;">
     <img src="./assets/image1.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

2. To create a new issue, click on **New**, then enter the **User ID**   and **Issue ID**.

    Select the appropriate Status Code. The following status options are available via dropdown:
    - Active
    - Inactive
    - Complete
    
    Please note that tracking is only performed for issues marked as **Active**. Add a brief Issue Description and click Save to complete the assignment. 

    <div style="text-align: left;">
     <img src="./assets/image2.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
       </div>

- Each screen or environment allows only one active issue at a time to maintain clarity and traceability. 
- Users can view assigned issues, making it easy to identify who is responsible for a change. 
 
 3. Any changes made are recorded on the Issue Assignment screen.

    -  Modifications to commands are logged in **Files** with the corresponding object name.
    - Data changes in Integrator are logged in **Seamles**. 
    - Modifications made through GUI or MOCA are reflected in **Tables** 

    <div style="text-align: left;">
     <img src="./assets/image3.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

## Creating a Rollout

To create a Rollout:

1. Click **Complete**.
2. Choose what you want to do:
   - **Commit** – to push changes to the repository.
   - **Rollout** – to create a rollout package.
   - **Both** – enable both options if you want to perform both actions together.
3. After selecting the required options and filling in the necessary fields, click **OK** to finish.

    <div style="text-align: left;">
      <img src="./assets/image4.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>

    Creating a rollout will also close the issue, the status will update from **Active (A)** to **Complete (C)**.

## Closing an Issue
Although creating a rollout automatically closes the issue, you can also close an issue manually if needed.

To do this:

1. Go to the **General** tab of the Issue Assignment screen.
2. Select the specific issue you want to close.
3. From the **Status Code** dropdown, change the status from **Active (A)** to **Complete (C)**.
4. Save your changes.

    <div style="text-align: left;">
      <img src="./assets/image70.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


This method gives you the flexibility to close an issue without creating a rollout.

---

<br><br>