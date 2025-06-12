# Concepts

## Problem
In WMS, many tables use auto-generated identity columns (`ID`) as primary keys. These IDs are unique to each environment and not manually assigned.

Using these IDs directly across environments (e.g., from development to production) can cause:

- Conflicts if the same ID exists for different data
- Data corruption or referential mismatches
- Inconsistencies due to environment-specific sequences

## Our Solution

1. **Triggers**

   Triggers are the foundation of the tracking mechanism. Whenever a change needs to be tracked, a corresponding trigger is created for the object.

    - These triggers detect **create**, **update**, or **delete** operations.
    - The purpose is to capture every significant change that results in the execution of a **MOCA command**.

2. **Logging Control**

    Smart DevOps tracks and logs all system changes, regardless of how they’re made:

    - **Screen-based (GUI) changes** are logged in relevant **tables**.
    - **MOCA command or backend changes** are captured and stored in **files**.
    - **Integrator-based changes**  are logged via **Seamless**.

3. **ID-Based Data Tracking**

    To enable precise and meaningful tracking, **descriptive views** are created for identity-based tables.

    - The views typically include key **codes**, their associated **descriptions**, and all other necessary fields relevant to tracking.
    - Tracking is performed on the basis of **codes and descriptions**, ensuring clarity.

     This approach is especially useful for data  where identifying records by ID alone is not user-friendly.

## Limitations

While Smart DevOps provides robust tracking , there are some limitations to be aware of:

- **Commands Not Tracked**  
  Actions performed using the following MOCA commands are **not tracked**:
  - `create record`
  - `change record`
  - `remove record`  
  These commands bypass the Smart DevOps tracking mechanism.

- **SQL-Based Changes Not Tracked**  
  Any data modifications made directly through **SQL queries** (e.g., `INSERT`, `UPDATE`, `DELETE`) are **not tracked** by Smart DevOps.
## Managing Deletes

Deletes are handled cautiously to prevent data loss or broken dependencies.

- **No direct `DELETE` statements** are used in control files
- Instead, standard BY commands like:
  - `Remove Movement Zone`
  - `Remove Category`

These ensure:

- Safe and validated delete operations
- Referential integrity is preserved
- Only non-dependent records are removed



## Control Files for Identity-Based Tables

A **control file (CTL)** instruct the system that what you need to do with that data.

### Key Principles

- Avoid using `INSERT`, `UPDATE`, or `DELETE` directly.
- Call commands like `Create Movement Zone`, passing relevant arguments **without IDs**.
- IDs are generated internally by the system to avoid environment-based conflicts.


---

<br><br>


