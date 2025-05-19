# Issue Assignment
Smart DevOps enables change tracking by issue assignment of a specific issue through GUI, ensuring accountability and control across all environments — whether Legacy, Web, or MOCA Client. 

The steps below will guide you through how the issue assignment process works in the GUI, helping you track changes effectively and with ease. 

1. Navigate to **Configuration → Extensions → OSSI – Issue Assignment** to access the Issue Assignment screen. 

    ![image1](./assets/image1.png) 

2. To create a new issue assignment, click on New, then enter the User ID and Issue ID. Select the appropriate Status Code—Active, Inactive, or Complete. Please note that tracking is only performed for issues marked as Active. Add a brief Issue Description and click Save to complete the assignment. 

    ![image2](./assets/image2.png)

- Each screen or environment allows only one active issue at a time to maintain clarity and traceability. 

- Users can view assigned issues, making it easy to identify who is responsible for a change. 
 
 3. Any changes made are recorded on the Issue Assignment screen. Modifications to commands are logged in **Files** with the corresponding object name, data changes in Integrator are logged in **Seamles** while changes made through GUI or MOCA are reflected in **Tables** 

    ![image3](./assets/image3.png)

 4. To finalize the issue, select Complete and then click Commit. This action updates the connected repository, such as Git or Bugzilla. Make sure all required fields are filled in. To enable rollout creation in the back end, ensure the Rollout option is selected. Select OK. 

    ![image4](./assets/image4.png)

- Change tracking can be disabled when necessary, offering flexibility in specific scenarios.  

- The system supports granular control over tracking policies (e.g., dscmst, configuration flags). 

- Unauthorized changes are prevented unless they are explicitly linked to an assigned issue, enforcing discipline in the development workflow. 

# Controlled Object Layout

SmartDevOps enforces a disciplined and consistent layout to manage different types of **controlled objects** in the Blue Yonder WMS environment. In this section, we’ll walk you through how each component is handled, and what best practices to follow so that your rollouts are clean, traceable, and consistent.



## Source Code

SmartDevOps keeps things clean and trackable. Here’s how we manage various source components:

- **MOCA Source & 3GL Logic**  
  All your custom logic is versioned and tracked within a repository. This makes it easy to trace back changes and ensure consistency across rollouts.

- **Binaries (executables, shared libraries, JARs)**  
  These are always treated as **precompiled artifacts**. That means no compiling during rollout — everything is ready to go and simply deployed.

- **Downloads, Client, and Mtfclient Components**  
  These must always have their source code maintained on the server. This keeps things transparent and reproducible.

- **Reports, Labels, and Scripts**  
  These are fully version-controlled. So every change you make is traceable — no surprises during deployment.

- **Rpweb Components**  
  Managed through MOCA and checked in from the server side. It ensures that changes are reflected properly and are easy to track.



## DDL (Data Definition Language)

When it comes to schema changes, structure and clarity are key.

- **Tables & Custom Columns**  
  Each table or column should be maintained in its **own dedicated file**. This improves visibility and makes troubleshooting much easier.

- **Avoid Generic Filenames**  
  Filenames like `jira001.sql` or `jira002.sql` aren’t helpful. Instead, name your files based on the table or object they modify — e.g., `add_column_to_orders.iesql`

  ![image5](./assets/image5.png)
- **Indexes**  
  - Each index must have its **own file**.
  - If you're modifying an index, include a **DROP statement** in the same file.
  - Indexes should **only be created via rollouts** — **never manually** by DBAs.
   ![image6](./assets/image6.png)
- **Sequences**  
  Define them clearly and ensure you have corresponding `sysctl` entries for consistency across environments.
    ![image7](./assets/image7.png)


## Data (Non-Delete)

For non-deletion data changes, organization is everything.

- **Folder Structure**  
  Follow the conventional `mload` style folder structure for clarity.

- **Naming Files**  
  Avoid incremental filenames like `jira001.csv`. Instead, name files based on their **primary key** or target object — this improves traceability.
  ![image8](./assets/image8.png)

- **Warehouse-Level Data (Optional)**  
  You may capture data at the warehouse level when necessary. Just ensure you maintain clear naming and structure.
   ![image9](./assets/image9.png)

- **File Management Strategy**  
  Have a consistent approach for handling files with sequence numbers to avoid confusion later.
   ![image10](./assets/image10.png)

- **Use Views for Exporting**  
  Always export data via **views** — this standardizes your approach and reduces errors.

- **Special Control Files**  
  Use them where needed — especially for advanced operations like conditional inserts or transformations.



## Data (Delete)

When dealing with data deletions, separation and clarity are vital.

- **Dedicated Folder**  
  Create a **separate folder** specifically for managing deletions.
  ![image11](./assets/image11.png)

- **Folder Structure**  
  Structure it similar to the `mload` folder — one subfolder **per table**.

- **Delete Operations**  
  - Each delete operation should have its **own file**.
  - Make sure each file references the **primary key** being deleted.
  - **Both hard and soft deletes** are supported.

- **Control Files**  
  Special control files are used to handle deletion logic properly — use them as needed for precision and reliability.
![image12](./assets/image12.png)



## Data (Integrator)

Integrator-related data changes have their own space:

- **Dedicated Folder**  
  Store all integrator-related data in its own **clearly named folder**.
![image13](./assets/image13.png)
- **Folder Structure**  
  Organize files logically by **group or function** for better readability.
![image14](./assets/image14.png)
![image15](./assets/image15.png)
- **Events and Outputs**  
  Each event should:
  - Clearly define its **arguments**.
  - Include **event outputs** that specify the correct **segments and fields** for proper execution.

---