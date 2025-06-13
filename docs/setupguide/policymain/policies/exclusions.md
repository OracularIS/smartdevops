# Policies for Exclusion

In some cases, it may be necessary to exclude certain data from tracking in Smart DevOps. Exclusion policies help you skip tracking for specific information that is not relevant.


## Exclude a Specific Column from Tracking (dscmst)

  If you want to stop tracking changes made to a specific **column** in a table, you can do so by setting up a policy. This is useful when certain fields are not critical for use.

  You can use this generic format for policy setup

  | `polcod`                 | `polvar`                      | `polval`         | `rtstr1`       | `rtnum1` |
  |--------------------------|-------------------------------|------------------|----------------|----------|
  | POLICY-NAME              | OBJECT-TABLE-TABLENAME        | EXCLUDE-COLNAM   | COLUMN-NAME    | 1       |

  - Replace **TABLENAME** in polvar with your target table.
  - Set **rtstr1** to the name of the column you want to exclude.
  - Set **rtnum1** to 1 to enable the exclusion.

  For example, to exclude the **wh_id** column from tracking in the dscmst table, you can set up the policy as shown below.

  | `polcod`                 | `polvar`                  | `polval`         | `rtstr1` | `rtnum1` |
  |--------------------------|----------------------------|------------------|----------|----------|
  | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-DSCMST        | EXCLUDE-COLNAM   | wh_id   | 1        |

  In this example, the description for the wh_id field in the dscmst table will not be tracked.

## Exclude a Specific Column from Tracking (sys_dsc_mst)
  If you want to exclude a specific column from being tracked in the SYS_DSC_MST table, you can do so by setting up a policy for it.

  This is helpful when changes to certain description-level fields are not essential and can be skipped from tracking.

  For example to exclude wh_id from being tracked in sys_dsc_mst the following policy must be setup.

  | `polcod`                  | `polvar`                   | `polval`         | `rtstr1`   | `rtnum1` |
  |-------------------------|----------------------------|----------------|----------|--------|
  | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-SYS_DSC_MST | EXCLUDE-COLNAM | wh_id  | 1     |


## Disabling Tracking for Child Tables

  When excluding a dataset from tracking, it is important to consider any related tables that may automatically get updated alongside the primary table.

  For example, if you're disabling tracking for a table like LES_MNU_OPT using a policy, remember that these tables may have associated descriptions stored in the **SYS_DSC_MST** table.

  In such cases, simply turning off tracking for LES_MNU_OPT is not sufficient, you must also set up a separate policy to disable related tracking for SYS_DSC_MST.  

  To do this, set the policy by disabling the table:

  | `polcod`                  | `polvar`                    | `polval`         | `rtstr1`   | `rtnum1` |
  |-------------------------|----------------------------|----------------|----------|--------|
  | USR-OSSI-VERSION-CONTROL | OBJECT-TABLE-SYS_DSC_MST | EXCLUDE-COLNAM | opt_nam  | 1     |

  - `rtnum1 = 1` → Tracking is **enabled** (ON)
  - `rtnum1 = 0` → Tracking is **disabled** (OFF)

## Exclude a Policy

  If you want to **exclude a specific policy**, you can set  it up by using the following format:

  | `polcod`                  | `polvar`               | `polval`         | `rtstr1`         | `rtnum1` |
  |---------------------------|------------------------|------------------|------------------|----------|
  | USR-OSSI-VERSION-CONTROL  | OBJECT-TABLE-POLDAT    | EXCLUDE-POLCOD   | POLICY-NAME  | 1        |

  For example to exclude policy for Allocate Inventory following policy will be enabled

  | `polcod`                  | `polvar`               | `polval`         | `rtstr1`          | `rtnum1` |
  |---------------------------|------------------------|------------------|-------------------|----------|
  | USR-OSSI-VERSION-CONTROL  | OBJECT-TABLE-POLDAT    | EXCLUDE-POLCOD   | ALLOCATE INV     | 1        |

  Setting `rtnum1` to `1` enables the exclusion of the specified policy from tracking.

---

<br><br>