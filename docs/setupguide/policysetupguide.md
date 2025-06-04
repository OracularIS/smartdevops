
# Policy Setup for Control Tracking
With Smart DevOps, you are not just pushing changes blindly. Every step is tracked, giving you full visibility into what is happening and when. This means you’ll always know:

Who is working on what - You can see exactly when an issue was assigned and to whom.

What changes are being made - Every edit, create, delete, or deployment is recorded.

## Global Tracking Setting

  Before you dive into the work, make sure global tracking is properly set up. These settings apply across your entire environment, so they are really important.

  - **Overall Setup**
    
    To properly initialize tracking in Smart DevOps, you need to configure the overall setup and **enable the required policies**, especially the SETUP policy. This is essential for Smart DevOps to begin managing and monitoring changes effectively.
    Here is a generic format to enable a Setup Policy:

    | `polcod`                  | `polvar` | `polval` |
    |---------------------------|----------|----------|
    | POLICY-NAME	 | SETUP    | ENABLED  |    


    For example, enabling the setup policy for USR-OSSI-VERSION-CONTROL :

    | `polcod`                  | `polvar` | `polval` |
    |---------------------------|----------|----------|
    | USR-OSSI-VERSION-CONTROL | SETUP    | ENABLED  |

    Without enabling the `SETUP` policy, Smart DevOps will **not** begin tracking changes, so be sure this is the first step in your configuration.

  - **Enable tag for any object**

    If you want to start tracking a specific object in Smart DevOps, you must first enable **object tracking**. 

    Here's a generic format for enabling a policy:
    | `polcod`                  | `polvar`                 | `polval` |
    |---------------------------|--------------------------|----------|
    | POLICY-NAME	 | OBJECT-TABLE-TABLENAME	     | ENABLED  |

    Here's an example to enable policy for table area master (asremst):

    | `polcod`                  | `polvar`                 | `polval` |
    |---------------------------|--------------------------|----------|
    | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-AREMST      | ENABLED  |

    Once this policy is enabled:
    - All changes made to the object (e.g. aremst) will be logged.
    - The object becomes part of your issue tracking and deployment workflow.
    - You ensure traceability and version control for every update.

## Policy setup for Version Control Systems
   To enable version control functionality in Smart DevOps, the following setup policies must be properly configured. These policies ensure that versioning features such as commit tracking, branching, and script integration work seamlessly within the Smart DevOps environment.

These settings are essential to connect your application with external version control tools and services like Git

Here's a generic format was setting up the policies fro version control systems like GIT.

| `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
|--------------------------|----------|----------------------|------------------------|
| POLICY-NAME              | SETUP    | CONFIGURATION-KEY    | CONFIGURATION-VALUE    |

**polcod:** Name of the policy group (e.g., USR-OSSI-VERSION-CONTROL)

**polvar:** Always set to SETUP for configuration settings

**polval:** Specific key that defines the configuration type (e.g., VERSION-CONTROL-SYSTEM)

**rtstr1:** The actual value or setting to apply

You need to enable these policies:

1. **Enable Git as Version Control System**

    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | VERSION-CONTROL-SYSTEM   | GIT    |

      Use case: Sets Git as the backend for version control.

2. **Set Git Repository**
    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-REPO   |  REPOSITORYNAME  

    Use case: Specifies the remote Git repository where changes will be committed.

    Replace the REPOSITORYNAME in rtsrt1 with your own repository name where changes will be committed.

3. **Set Active Git Branch**	

    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-ACTIVE-BRANCH   | BRANCHNAME    |

    Use case: Defines the current working branch used for commits.

    Replace the BRANCHNAME in rtsrt1 with your own branch name used for commits.

4. **Set Main Git Branch**
    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-MAIN-BRANCH   | BRANCHNAME    |

    Use case: Identifies the main (default) branch of the repository.

    Replace the BRANCHNAME in rtsrt1 with your own branch name.

5. **Set Git Executable Path**

    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-EXEC-PATH   | PATH    |

    Use case: Points to the executable path of the Git CLI used by the system.
    
    Replace PATH in rtsrt1 with executable directory path of your system for GIT.


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
  
    Lets say you are creating a movement zone, there might be automatic generation of areas and locations.
    
     But what if you only care about tracking the creation of the **movement zone itself**, and not all the related sub-elements?

      With this feature, you can **disable tracking temporarily** while the transaction is in progress by enabling the policy for it.

     Generic format for policy to disable tracking for action is:
       | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | POLICY-NAME  | OBJECT-TABLE-TABLENAME   | DISABLE-ON-ACTION |  

      **polval** here defines the specific action during which tracking should be disabled such as DISABLE-ON-CHANGE (for updates), DISABLE-ON-REMOVE (for deletions), or DISABLE-ON-ADD (for insertions).  

      Here's the policy you need to set for disabling change track for movement zone:
      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-MOV_ZONE  | DISABLE-ON-CHANGE |

      Similarly, you can stop tracking while deleting a movement zone by setting the policy mentioned below

      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-MOV_ZONE  | DISABLE-ON-REMOVE |
      
      Similary, you can stop tracking while adding data by setting the policy mentioned below
     
      | `polcod`                  | `polvar`          | `polval`          |
      |-------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-MOV_ZONE | DISABLE-ON-ADD |

      This gives you a clear, high-level tracking without cluttering your issue logs with unnecessary low-level operations.
  
  - **Excluding subset of data during tracking**

    Smart DevOps provides flexibility when it comes to excluding specific pieces of data from tracking.

    There may be situations where you do not want every field or change to be tracked for example, when certain columns like **descriptions or timestamps** are not critical to your version history.

    Here’s a generic format for policies that exclude tracking for specific fields in a table or object:

      | `polcod`                  | `polvar`                            | `polval`   | `rtstr1`                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | POLICY-NAME	 | OBJECT-TABLE-POLDAT       | EXCLUDE-COLNAM or EXCLUDE-POLCOD	 | FIELD-NAME|



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

    Here's a generic format for Excluding Specific Data Using Trigger Filters:
      | `polcod`                  | `polvar`                            | `polval`   | `rtstr1`                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | POLICY-NAME	 | OBJECT-TABLE-TABLENAME    | TRIGGER-FILTER | FILTER-FUNCTION-NAME|      


    Here's an example for location master (locmst)
      | `polcod`                  | `polvar`                            | `polval`   | `rtstr1`                        |
      |-------------------------|------------------------------------|----------|----------------------------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-LOCMST     | TRIGGER-FILTER | uc_ossiissue_filter_locmst|    

  To exclude specific data, you simply enable or modify the policy associated with it.
  
---

<br><br>


