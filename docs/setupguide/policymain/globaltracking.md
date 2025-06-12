# Global Tracking Setting

Before you dive into the work, make sure global tracking is properly set up. These settings apply across your entire environment, so they are really important.

## **Overall Setup**

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


## Object-Specific Policy Setup

If you start tracking a specific object in Smart DevOps, you must first enable **object tracking**. 

 Here's a generic format for enabling a policy:
| `polcod`                  | `polvar`                 | `polval` |`rtnum1`                 |
|---------------------------|--------------------------|----------| --------------------------|
 POLICY-NAME	 | OBJECT-TABLE-TABLENAME	     | ENABLED  | 1 |

Here's an example to enable policy for table area master (aremst):

| `polcod`                  | `polvar`                 | `polval` |`rtnum1`                 |
|---------------------------|--------------------------|----------|--------------------------|
| USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-AREMST      | ENABLED  | 1 |

The `rtnum1` field controls whether object tracking is active:

- `rtnum1 = 1` → Tracking is **enabled** (ON)
- `rtnum1 = 0` → Tracking is **disabled** (OFF)

Once this policy is enabled:
- All changes made to the object (e.g. aremst) will be logged.
- The object becomes part of your issue tracking and deployment workflow.
- You ensure traceability and version control for every update.

## Warehouse-Specific Policy Setup

This policy is used to control which warehouse(s) a user can track and work with. If you want to enable tracking for a **specific warehouse** or **multiple warehouses** based on environment variables, you need to define the following policy:


| `polcod`                  | `polvar` | `polval` | `rtnum2` |
|---------------------------|----------|----------|----------|
| USR-OSSI-VERSION-CONTROL  | SETUP    | ENABLED  | 1        |

Once this policy is enabled:

- Tracking is activated for all warehouses defined through environment variables.
- The system determines the applicable warehouse(s) using the `check_usr_issue_assignment_active` command.
- It uses the following environment variables to detect active warehouse IDs:
  - `uc_ossi_issue_assignment_active_detect_wh_id`
  - `uc_ossi_issue_assignment_active_detect_wh_id_list`

These variables help dynamically apply tracking based on the user’s context, enabling more flexible and accurate warehouse-level control.

## Including Specific Rows for Tracking 

If you want to include only specific rows for tracking, you can do this by setting up a policy using a **trigger filter**. This allows you to define logic that selects which data should be tracked from a particular table.

Here is a general format for the policy you need to setup

| `polcod`                 | `polvar`                      | `polval`        | `rtstr1`                     |
|--------------------------|-------------------------------|------------------|-------------------------------|
| POLICY-NAME              | OBJECT-TABLE-TABLENAME        | TRIGGER-FILTER   | FILTER-FUNCTION-NAME         |

- Replace `TABLENAME` in `polvar` with the actual table you want to track.
- `rtstr1` should contain the name of the function or command that defines which rows to include for tracking.

---

Here is an example for tracking a specifc row for location master (locmst)

| `polcod`                 | `polvar`                      | `polval`        | `rtstr1`                        |
|--------------------------|-------------------------------|------------------|----------------------------------|
| USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-LOCMST           | TRIGGER-FILTER   | uc_ossiissue_filter_locmst       |

---

Only the rows matched by the filter function will be tracked.

## Tracking Exclusions

1. **Exclude a Specific Column from Tracking**

    If you want to stop tracking changes made to a specific **column** in a table, you can do so by setting up a policy. This is useful when certain fields are not critical for use.

    You can use this generic format for policy setup
    | `polcod`                 | `polvar`                      | `polval`         | `rtstr1`       | `rtnum1` |
    |--------------------------|-------------------------------|------------------|----------------|----------|
    | POLICY-NAME              | OBJECT-TABLE-TABLENAME        | EXCLUDE-COLNAM   | COLUMN-NAME    | 1        |

    - Replace `TABLENAME` in `polvar` with your target table.
    - Set `rtstr1` to the name of the **column you want to exclude**.
    - Set `rtnum1` to `1` to enable the exclusion.

    For example, to exclude the **wh_id** column from tracking in the dscmst table, you can set up the policy as shown below.
    | `polcod`                 | `polvar`                  | `polval`         | `rtstr1` | `rtnum1` |
    |--------------------------|----------------------------|------------------|----------|----------|
    | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-DSCMST        | EXCLUDE-COLNAM   | wh_id   | 1        |

    In this example, the description for the wh_id field in the dscmst table will not be tracked.


2. **Disabling Tracking for Related Tables**

    When excluding a dataset from tracking, it is important to consider any related tables that may automatically get updated alongside the primary table.

    For example, if you're disabling tracking for a table like LES_MNU_OPT using a policy, remember that these tables may have associated descriptions stored in the **SYS_DSC_MST** table.

    In such cases, simply turning off tracking for LES_MNU_OPT is not sufficient, you must also set up a separate policy to disable tracking for SYS_DSC_MST.  

    To do this, set the policy by disabling the table:

    | `polcod`                 | `polvar`            | `polval`       | `rtnum` |
    |--------------------------|---------------------|----------------|---------|
    | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-SYS_DSC_MST | ENABLED | 0       |

    - `rtnum1 = 1` → Tracking is **enabled** (ON)
    - `rtnum1 = 0` → Tracking is **disabled** (OFF)

3. **Exclude a Policy**

    If you want to **exclude a specific policy**, you can set  it up by using the following format:

    | `polcod`                  | `polvar`               | `polval`         | `rtstr1`         | `rtnum1` |
    |---------------------------|------------------------|------------------|------------------|----------|
    | USR-OSSI-VERSION-CONTROL  | OBJECT-TABLE-POLDAT    | EXCLUDE-POLCOD   | `<POLICY-NAME>`  | 1        |

    For example to exclude policy for Allocate Inventory following policy will be enabled

    | `polcod`                  | `polvar`               | `polval`         | `rtstr1`          | `rtnum1` |
    |---------------------------|------------------------|------------------|-------------------|----------|
    | USR-OSSI-VERSION-CONTROL  | OBJECT-TABLE-POLDAT    | EXCLUDE-POLCOD   | ALLOCATE INV     | 1        |

    Setting `rtnum1` to `1` enables the exclusion of the specified policy from tracking.



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


  
---

<br><br>