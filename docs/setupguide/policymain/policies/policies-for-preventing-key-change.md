# Policies for Preventing Key Change

Some objects in Blue Yonder (BY) do not have a dedicated, immutable unique-key column. In these cases, Smart DevOps relies on a combination of the object's ID and its description or name to identify the object consistently.

Changing the description or name of an object that is already referenced by issue assignments can break that association. The **Prevent Key Change** policies help avoid this problem by preventing changes to configured key values when the functionality is enabled.

## Why Is This Functionality Needed?

For many BY objects, such as pick zones and location types, a `cod` field provides a unique key. However, not every object has an equivalent immutable key. For example, allocation search paths do not provide a similar column, so the US English description is used as part of the object's identity.

For these objects, the combination of the object's ID and its description or name is treated as a unique-key pair. If the description or name changes, the system may no longer be able to match the object consistently with data that has already been recorded or deployed.

This can create problems for issue assignments and rollout/version-control data:

- CSV files represent data as it exists at the time they are generated; they do not necessarily preserve every earlier value.
- An object can be changed several times before the final change is committed and deployed. For example, a description might change from **A** to **B**, and then from **B** to **C**.
- If different environments have different change histories, the description recorded in a CSV file may not reliably represent the object's earlier state.
- Changing a value used as part of the object's unique identity can make existing references ambiguous or prevent the system from associating the object correctly.

The solution is to prevent changes to configured key descriptions or names when they are being used as part of the object's identity. A pre-trigger checks the current value against the requested value and raises an error if a change is detected.

## How the Functionality Works

The functionality is controlled entirely through policies in `USR-OSSI-VERSION-CONTROL`.

### Policy Configuration

The policy uses the following values:

| `polcod` | `polvar` | `polval` | `rtnum1` | 
|---|---|---|---|---|
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `DEFAULT` | `1` or `0` | 

- `polcod` identifies the policy group.
- `polvar` identifies the key-change prevention functionality.
- `polval` is either `DEFAULT` or the name of a specific table.
- `rtnum1` controls whether the functionality is enabled: `1` enables it and `0` disables it.
- `wh_id` must be set to `----`.

The system first looks for a policy matching the target table name. If no table-specific policy is found, it uses the `DEFAULT` policy. If neither value is configured, the functionality defaults to enabled (`1`).

**Important:** A table-specific policy takes precedence over `DEFAULT`. This allows the functionality to be enabled or disabled for individual tables independently of the default setting.

### Default and Table-Specific Policies

- **Default policy:** Controls the behavior for tables without a table-specific policy.
- **Table-specific policy:** Controls the behavior for a particular table and overrides the default setting for that table.

Use `rtnum1 = 1` to enable prevention and `rtnum1 = 0` to disable it. Table-specific policies can be used to include or exclude individual tables according to customer requirements.

## Current Policy Configuration

The following policies define the tables currently configured for this functionality.

| `polcod` | `polvar` | `polval` | `rtnum1` |
|---|---|---|---|
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `ALLOC_SEARCH_PATH` | null |
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `CNTZON` | null |
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `DEFAULT` | `0` |
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `LOC_TYP` | null |
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `MOV_ZONE` | null |
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `PCK_ZONE` | null|
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `STO_CONFIG` | null|
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `STO_ZONE` | null |
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `ZONMST` | null |

The table-specific rows identify the tables that have been selected for this functionality. The `DEFAULT` row is not a table; it is the fallback setting.

In the configuration above, `DEFAULT` is set to `0`, so prevention is disabled by default. The table-specific rows should have `rtnum1` configured as `1` or `0` to explicitly enable or disable the behavior for each listed table, this value is intially started as null as by default no exceptions are being done.

### Adding or Updating Table Policies

Additional tables can be configured as required by a customer. To add a table, create a policy row with:

| `polcod` | `polvar` | `polval` | `rtnum1` | `wh_id` |
|---|---|---|---|---|
| `USR-OSSI-VERSION-CONTROL` | `PREVENT-KEY-COLVAL-CHANGE` | `TABLE_NAME` | `1` or `0` | `----` |

Replace `TABLE_NAME` with the target table name. Set `rtnum1` to `1` to enable key-change prevention for that table, or `0` to disable it.

Only tables that have a relevant header-level description or unique-key value should be configured. Child tables that do not own the description or unique-key value generally do not need this pre-trigger.

## Error Handling

When a key change is detected for a table where prevention is enabled, the system raises the following policy-based error:

| `polcod` | `polvar` | `wh_id` | `polval` |
|---|---|---|---|
| `USR-OSSI-VERSION-CONTROL` | `ERROR-CODES` | `----` | `EUSR_OSSI_ISSUE_TABLE_KEY_CHANGE_NOT_ALLOWED` |

The error message is configured in `rtstr1` (and can be continued in `rtstr2` if it exceeds the available length):

```text
Table ^uc_table_name^, PK column ^uc_pk_colnam^, UK column ^uc_uk_colnam^, PK colval ^uc_pk_colval^, UK colval ^uc_uk_colval^. Changing is not allowed
```

The message identifies the table, primary-key column and value, unique-key column and requested value. This helps explain which attempted change was rejected.

## Command: `check ossi change for key description`

The command `check ossi change for key description` is implemented in `ossiissue` and is called as a **pre-trigger** by the relevant change commands.

## Summary

The **Prevent Key Change** functionality protects object identity where BY does not provide an immutable unique-key field. It uses policy-driven checks to prevent changes to configured descriptions or names that form part of the object's unique-key pair. The default behavior and each table's behavior can be controlled independently, and additional tables can be added to meet customer requirements.
