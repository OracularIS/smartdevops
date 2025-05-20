# Setup Guide 
This guide will walk you through how to properly set up and manage tracking in Smart DevOps. Whether you're assigning issues, enabling policies, or working with regular objects, everything you need to know is right here.

# Control Tracking
With Smart DevOps, you're not just pushing changes blindly. Every step is tracked, giving you full visibility into what’s happening and when. This means you’ll always know:

Who’s working on what — You can see exactly when an issue was assigned and to whom.

What changes are being made — Every edit, create, delete, or deployment is recorded.

- **Global Tracking Setting**

  Before you dive into the work, make sure global tracking is properly set up. These settings apply across your entire environment, so they’re really important.

  - **Overall Setup**
    
    To properly initialize tracking in Smart DevOps, you need to configure the overall setup and **enable the required policies**, especially the SETUP policy. This is essential for Smart DevOps to begin managing and monitoring changes effectively.

    Make sure the following policy is set up as shown:

    | `polcod`                  | `polvar` | `polval` |
    |---------------------------|----------|----------|
    | USR-OSSI-VERSION-CONTROL | SETUP    | ENABLED  |

    Without enabling the `SETUP` policy, Smart DevOps will **not** begin tracking changes, so be sure this is the first step in your configuration.

  - **Enable tag for any object**

    If you want to start tracking a specific object in Smart DevOps, you must first **object tracking**. 

    Here’s the policy you need to set:

    | `polcod`                  | `polvar`                 | `polval` |
    |---------------------------|--------------------------|----------|
    | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-AREMST      | ENABLED  |

    Once this policy is enabled:
    - All changes made to the object will be logged.
    - The object becomes part of your issue tracking and deployment workflow.
    - You ensure traceability and version control for every update.



- **Regular Objects - without identity columns**

  In Smart DevOps, you can track all changes for regular objects that do not have identity columns.

  This means even if a table or object doesn’t use an auto-generated primary key, Smart DevOps is still capable of capturing and versioning every update made to it.

- **Regular Objects - with identity columns**

  Similarly, objects with identity columns (such as auto-incrementing primary keys) are fully supported.
  Smart DevOps will track row insertions, updates and eletions
  based on the identity column, ensuring precise version control.

- **Integrator Objects**

  Smart DevOps also tracks all the changes made through integrator. 

  No extra configuration needed — as long as tracking is enabled for the related object, all integrator-related changes will be captured automatically.

- **Special Use Cases**
  - **Disable issue tracking in the middle of transaction**
    
    Smart DevOps gives you flexibility when it comes to tracking changes — and one of the powerful features is the ability to **disable issue tracking in the middle of a transaction**.

    This is especially helpful when:

    - You don’t want to track every step of a complex operation.
    - You only care about the final outcome of a transaction —  not the entire chain of changes that lead up to it.
  
    Lets say you are creating a warehouse, there might be automatic generation of zones, areas and locations.
      
     But what if you only care about tracking the creation of the **warehouse itself**, and not all the related sub-elements?

      With this feature, you can **disable tracking temporarily** while the transaction is in progress by enabling the policy for it.

      Hers's the policy you need to set
      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-WH  | DISABLE-ON-CHANGE |

     Similarly, you can stop tracking while deleting a warehouse by setting the policy mentioned below

      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-WH  | DISABLE-ON-REMOVE |

      This gives you a clear, high-level tracking without cluttering your issue logs with unnecessary low-level operations.
  
  - **Excluding subset of data during tracking**

    Smart DevOps provides flexibility when it comes to excluding specific pieces of data from tracking.

    There may be situations where you don’t want every field or change to be tracked — for example, when certain columns like **descriptions or timestamps** are not critical to your version history.

    - **How to do it for policies**
    
      If you want to skip tracking for specific fields, you can simply **disable the policy** associated with that field like
      | polcod                  | polvar                            | polval   | rtstr1                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-POLDAT       | EXCLUDE-POLCOD | ALLOC-LOC-LOCK|

    - **How to do it for dscmst**

       If you don’t want to track the **DESCRIPTION** field (or any specific field), you can simply **disable the policy** related to that field.

      Here's an example:
       | polcod                  | polvar                            | polval   | rtstr1                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-DSCMST      | EXCLUDE-COLNAM | wh_id|






  

# Building Rollouts Without Integrated Version Control
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

