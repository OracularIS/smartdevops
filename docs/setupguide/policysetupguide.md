
# Policy Setup for Control Tracking
With Smart DevOps, you are not just pushing changes blindly. Every step is tracked, giving you full visibility into what is happening and when. This means you’ll always know:

Who is working on what - You can see exactly when an issue was assigned and to whom.

What changes are being made - Every edit, create, delete, or deployment is recorded.

## Global Tracking Setting

  Before you dive into the work, make sure global tracking is properly set up. These settings apply across your entire environment, so they are really important.

  - **Overall Setup**
    
    To properly initialize tracking in Smart DevOps, you need to configure the overall setup and **enable the required policies**, especially the SETUP policy. This is essential for Smart DevOps to begin managing and monitoring changes effectively.

    Make sure the following policy is set up as shown:

    | `polcod`                  | `polvar` | `polval` |
    |---------------------------|----------|----------|
    | USR-OSSI-VERSION-CONTROL | SETUP    | ENABLED  |

    Without enabling the `SETUP` policy, Smart DevOps will **not** begin tracking changes, so be sure this is the first step in your configuration.

  - **Enable tag for any object**

    If you want to start tracking a specific object in Smart DevOps, you must first enable **object tracking**. 

    Here's an example to enable it:

    | `polcod`                  | `polvar`                 | `polval` |
    |---------------------------|--------------------------|----------|
    | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-AREMST      | ENABLED  |

    Once this policy is enabled:
    - All changes made to the object (e.g. aremst) will be logged.
    - The object becomes part of your issue tracking and deployment workflow.
    - You ensure traceability and version control for every update.



## Regular Objects - without identity columns

  In Smart DevOps, you can track all changes for regular objects that do not have identity columns.

  This means even if a table or object does not use an auto-generated primary key, Smart DevOps is still capable of capturing and versioning every update made to it.

## Regular Objects - with identity columns

  Similarly, objects with identity columns (such as auto-incrementing primary keys) are fully supported.
  Smart DevOps will track row insertions, updates and eletions
  based on the identity column, ensuring precise version control.

## Integrator Objects

  Smart DevOps also tracks all the changes made through integrator. 

  No extra configuration needed - as long as tracking is enabled for the related object, all integrator-related changes will be captured automatically.

## Special Use Cases
  - **Disable issue tracking in the middle of transaction**
    
    Smart DevOps gives you flexibility when it comes to tracking changes — and one of the powerful features is the ability to **disable issue tracking in the middle of a transaction**.

    This is especially helpful when:

    - You don’t want to track every step of a complex operation.
    - You only care about the final outcome of a transaction -  not the entire chain of changes that lead up to it.
  
    Lets say you are creating a warehouse, there might be automatic generation of zones, areas and locations.
      
     But what if you only care about tracking the creation of the **warehouse itself**, and not all the related sub-elements?

      With this feature, you can **enable tracking temporarily** while the transaction is in progress by enabling the policy for it.

      Here's the policy you need to set
      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-WH  | DISABLE-ON-CHANGE |

      Similarly, you can stop tracking while deleting a warehouse by setting the policy mentioned below

      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-WH  | DISABLE-ON-REMOVE |
      
      Similary, you can stop tracking while adding data by setting the policy mentioned below
     
      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-MOV_ZONE | DISABLE-ON-ADD |

      This gives you a clear, high-level tracking without cluttering your issue logs with unnecessary low-level operations.
  
  - **Excluding subset of data during tracking**

    Smart DevOps provides flexibility when it comes to excluding specific pieces of data from tracking.

    There may be situations where you do not want every field or change to be tracked for example, when certain columns like **descriptions or timestamps** are not critical to your version history.

    - **How to do it for policies**
    
      If you want to skip tracking for specific fields, you can simply **enable the policy** associated with that field like
      | `polcod`                  | `polvar`                            | `polval`   | `rtstr1`                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-POLDAT       | EXCLUDE-POLCOD | ALLOC-LOC-LOCK|

    - **How to do it for dscmst**

       If you do not want to track the **DESCRIPTION** field (or any specific field), you can simply **enable the policy** related to that field.

      Here's an example:
       | `polcod`                  | `polvar`                            | `polval`   | `rtstr1`                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-DSCMST      | EXCLUDE-COLNAM | wh_id|

  - **How It Works Generally**

     You can control what gets tracked by configuring tracking policies. These policies define which tables, columns, or objects should be excluded from version control.

    If you want to exclude specific data entries in a table like LOCMST, add a policy with trigger filter and required fields or keys based on your use case.

    Here's an example
      | `polcod`                  | `polvar`                            | `polval`   | `rtstr1`                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-LOCMST     | TRIGGER-FILTER | uc_ossiissue_filter_locmst|    

  To exclude specific data, you simply enable or modify the policy associated with it.
  
---

<br><br>


