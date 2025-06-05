
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
  | POLICY-NAME               | SETUP    | ENABLED  |

  For example, enabling the setup policy for USR-OSSI-VERSION-CONTROL:

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
   To enable version control functionality in Smart DevOps, you must properly set up the related policies.
    These policies ensure that versioning features such as commit tracking, branching, and script integration work seamlessly within the Smart DevOps environment.

These settings are essential to connect your application with external version control tools and services like Git

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

    Smart DevOps provides flexibility when it comes to exclude specific data from tracking.

    There may be situations where you do not want every field or change to be tracked for example, when certain columns like **descriptions or timestamps** are not critical to your version history.
  
    - **Excluding an Entire Table from Tracking**

      Smart DevOps allows you to exclude specific tables from tracking by setting policies.

      To disable tracking for a table, create a policy entry where the **rtnum** is set to **0**. To re-enable tracking, set rtnum back to 1.

      For example, to stop tracking changes to the `LES_MNU_OPT` table, set the policy as shown below. 
      
      This ensures that no insert, update, or delete operations on this table are recorded by the tracking system.

      | `polcod`                 | `polvar`                   | `polval`       | `rtnum` |
      |--------------------------|----------------------------|----------------|---------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-LES_MNU_OPT   | EXCLUDE-POLCOD | 0       |

       You can follow the same approach to disable tracking for **any table** by replacing `LES_MNU_OPT` with the name of your target  table(s).  

      Just update the value of `OBJECT-TABLE-<TABLE_NAME>` in the `polvar` field accordingly.

    - **Exclude Description from Tracking**

      If you do not want to track the `DESCRIPTION`, Smart DevOps provides two approaches to achieve this:

      1. **Remove the Description Table from Tracking**

         If tracking description data is not required for your process, you can simply exclude the entire description table from tracking.

          To do this, set the policy by disabling the table:

          | `polcod`                 | `polvar`            | `polval`       | `rtnum` |
          |--------------------------|---------------------|----------------|---------|
          | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-DSCMST | EXCLUDE-POLCOD | 0       |

          ---
        2. **Disable Tracking for Specific Fields Only**

           If you still want to track most changes in the table but exclude specific fields , you can selectively disable tracking for those fields by setting up policy related to it.

            For example, while creating a warehouse, if you want to **exclude the `wh_id` field** from tracking in the `DSCMST` table:

            | `polcod`                 | `polvar`            | `polval`       | `rtstr1` |
            |--------------------------|---------------------|----------------|----------|
            | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-DSCMST | EXCLUDE-COLNAM | wh_id    |
            ---
            You can list any desired **column name** in the `rtstr1` field to exclude it from tracking.

    - **Excluding SYS_DSC_MST**

        When excluding a dataset from tracking, it is important to consider any related tables that may automatically get updated alongside the primary table.

        For example, if you're disabling tracking for a table like LES_MNU_OPT using a policy, remember that these tables may have associated descriptions stored in the SYS_DSC_MST table.

        In such cases, simply turning off tracking for LES_MNU_OPT is not sufficient, you must also configure a separate policy to disable tracking for SYS_DSC_MST.  
  
        To do this, set the policy by disabling the table:

        | `polcod`                 | `polvar`            | `polval`       | `rtnum` |
        |--------------------------|---------------------|----------------|---------|
         | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-SYS_DSC_MST | EXCLUDE-POLCOD | 0       |

        ---       
    - **How to Setup a Policy to Exclude a Field from Tracking**

      Smart DevOps allows you tracking by excluding specific fields. This is useful when certain fields are not relevant for change tracking and can be safely omitted.

      You can set up a policy to exclude specific fields in any table by using the generic format below:

      | `polcod`                  | `polvar`                            | `polval`           | `rtstr1`         |
      |---------------------------|--------------------------------------|--------------------|------------------|
      | POLICY-NAME               | OBJECT-TABLE-POLDAT                 | EXCLUDE-COLNAM or EXCLUDE-POLCOD | FIELD-NAME        |

      - `polcod`: The name of the version control policy, e.g., `USR-OSSI-VERSION-CONTROL`.
      - `polvar`: Replace `POLDAT` with the actual table name for which the field exclusion is required.
      - `polval`: Set this to either `EXCLUDE-COLNAM` (to exclude a column) or `EXCLUDE-POLCOD` (to exclude a table).
      - `rtstr1`: Replace this with the field or column name you want to exclude from tracking.

      #### Example

      To skip tracking for the field `ALLOC-LOC-LOCK` in a table named `POLDAT`, your policy would look like this:

      | `polcod`                  | `polvar`                            | `polval`        | `rtstr1`         |
      |---------------------------|--------------------------------------|------------------|------------------|
      | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-POLDAT                 | EXCLUDE-POLCOD   | ALLOC-LOC-LOCK   |

      You can apply this same format to any other table by updating the `polvar` value to include your target table name, and replace `rtstr1` with the field you wish to exclude from tracking.

  - **How It Works Generally**

     You can control what gets tracked by setting tracking policies. These policies define which tables, columns, or objects should be excluded from version control.

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


