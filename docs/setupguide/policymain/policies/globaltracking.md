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
|---------------------------|--------------------------|----------|--------------------------|
| POLICY-NAME | OBJECT-TABLE-TABLENAME      | ENABLED  | 1 |

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