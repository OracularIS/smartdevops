# Policies for Controlled Tracking

Before you dive into the work, make sure global tracking is properly set up. These settings apply across your entire environment, so they are really important.

## **Global Policy**

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


## Row Specific Policy

If you want to include only specific rows for tracking, you can do this by setting up a policy using a **trigger filter**. This allows you to define logic that selects which data should be tracked from a particular table.

Here is a general format for the policy you need to setup

| `polcod`                 | `polvar`                      | `polval`        | `rtstr1`                     |
|--------------------------|-------------------------------|------------------|-------------------------------|
| POLICY-NAME              | OBJECT-TABLE-TABLENAME        | TRIGGER-FILTER   | FILTER-FUNCTION-NAME         |

- Replace `TABLENAME` in `polvar` with the actual table you want to track.
- `rtstr1` should contain the name of the function or command that defines which rows to include for tracking.

Here is an example for tracking a specifc row for location master (locmst)

| `polcod`                 | `polvar`                      | `polval`        | `rtstr1`                        |
|--------------------------|-------------------------------|------------------|----------------------------------|
| USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-LOCMST           | TRIGGER-FILTER   | uc_ossiissue_filter_locmst       |

Only the rows matched by the filter function will be tracked.

## Rollout Naming Convention Policy
To ensure consistent naming for rollouts, you can set up a policy that defines the naming convention.  

Here is how the naming is structured:

- **ROLLOUT-NAME-PREFIX-EXPR**

   This defines the initial part of the rollout name

   | `polcod`                 | `polvar`                      | `polval`        | `rtstr1`                        |
   |--------------------------|-------------------------------|------------------|----------------------------------|
  | USR-OSSI-VERSION-CONTROL | SETUP           | ROLLOUT-NAME-PREFIX-EXPR  | 'USR001_QUASAR_CONFIG'       |

  You can update the rtstr1 value with your desired prefix to match your naming needs.

- **ROLLOUT-NAME-SEP**

  This policy defines the separator character (such as an underscore _, dash -, or any other symbol) that appears between the components of the rollout name. The separator ensures clarity and consistency in rollout naming. 

  | `polcod`                 | `polvar`                      | `polval`        | `rtstr1`                        |
  |--------------------------|-------------------------------|------------------|----------------------------------|
  | USR-OSSI-VERSION-CONTROL | SETUP           | ROLLOUT-NAME-SEP  | __       |

  The `rtstr1` value can be modified by the user as needed to match the preferred naming format.

- **ROLLOUT-NAME-MINOR-VERSION-LOOKUP-EXPR**

  The ROLLOUT-NAME-MINOR-VERSION-LOOKUP-EXPR variable is used to define the final part of the rollout name. It allows you to build this portion of the name using a combination of expressions, system variables, and separators.

  | `polcod`                 | `polvar`                      | `polval`        | `rtstr1`                        |
  |--------------------------|-------------------------------|------------------|----------------------------------|
  | USR-OSSI-VERSION-CONTROL | SETUP           | ROLLOUT-NAME-MINOR-VERSION-LOOKUP-EXPR  | @uc_rollout_name_sep \|\| '*'      |

  The `rtstr1` value can be modified by the user as needed to match the preferred name. 

- **ROLLOUT-NAME-MINOR-VERSION-POS**

  The ROLLOUT-NAME-MINOR-VERSION-POS variable is used to define the position of the minor version in the rollout name. 
  
  This helps structure the name properly by indicating where the minor version should appear in relation to other elements like the prefix and major version.

  | `polcod`                 | `polvar` | `polval`                        | `rtstr1` | `rtnum1` |
  |--------------------------|----------|----------------------------------|----------|----------|
  | USR-OSSI-VERSION-CONTROL | SETUP    | ROLLOUT-NAME-MINOR-VERSION-POS | This is position of minor version        | 7        |

  The `rtnum1` value can be modified by the user to adjust where the minor version appears in the name format.

- **ROLLOUT-NAME-MAJOR-VERSION-POS**

  This variable defines the position where the major version number should appear in the rollout name. By specifying this position, the system knows exactly where to insert the major version in the final name format.

  | `polcod`                 | `polvar` | `polval`                         | `rtstr1` | `rtnum1` |
  |--------------------------|----------|----------------------------------|----------|----------|
  | USR-OSSI-VERSION-CONTROL | SETUP    | ROLLOUT-NAME-MAJOR-VERSION-POS  | This is the position of major version in the rollout name       | 5        |

  You can modify the `rtnum1` value to set your desired major version position in the rollout name.








  
---

<br><br>