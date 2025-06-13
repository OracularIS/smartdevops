# Concepts

## Problem
Earlier, all commits were done manually, making the process time consuming and prone to errors. One of the major challenges was handling ID-based data in the BY WMS system.

Many WMS tables use auto-generated identity columns (IDs) as primary keys. These IDs are unique to each environment (like development or production) and are not manually assigned. This creates serious issues when moving data across environments:

- The same ID might point to different records in each environment.
- This can lead to conflicts, data corruption, or broken references.
- Developers had to manually adjust and trace these IDs, which was   inefficient and risky.

## Our Solution

The following key features were introduced in Smart DevOps to overcome earlier challenges and improve efficiency:

1. **Triggers**

   Triggers are the foundation of the tracking mechanism. Whenever a change needs to be tracked, a corresponding trigger is created for the object.

    - These triggers detect **create**, **update**, or **delete** operations.
    - The purpose is to capture every significant change that results in the execution of a MOCA command.

2. **Logging Control**

    Smart DevOps tracks and logs all system changes, regardless of how they’re made:

    - **Screen-based (GUI) changes** are logged in relevant tables.
    - **MOCA command or backend changes** are captured and stored in files.
    - **Integrator-based changes**  are logged via Seamless.

3. **ID-Based Data Tracking**

    To enable precise and meaningful tracking, **descriptive views** are created for identity-based tables.

    - The views typically include key codes, their associated descriptions, and all other necessary fields relevant to tracking.
    - Tracking is performed on the basis of codes and descriptions, ensuring clarity.

     This approach is especially useful for data  where identifying records by ID alone is not user-friendly.

4. **Managing Deletes**

    Deletes are managed using **standard BY commands** like Remove Movement Zone and Remove Category instead of direct DELETE statements in control files.

    This approach ensures:
    - Safe and validated deletion operations  
    - Dependent records are protected from accidental removal

5. **Control Files for Identity-Based Tables**

    A control file (CTL) instruct the system that what you need to do with that data.

    Use the following best practices when dealing with identity-based tables:

    - Avoid using **INSERT**, **UPDATE**, or **DELETE** directly.
    - Call commands like Create Movement Zone, passing relevant arguments **without IDs**.
    - IDs are generated internally by the system to avoid environment-based conflicts.

6. **Regular Objects - without identity columns**

   In Smart DevOps, you can track all changes for regular objects that do not have identity columns.

    This means even if a table or object does not use an auto-generated primary key, Smart DevOps is still capable of capturing and versioning every update made to it.

7. **Regular Objects - with identity columns**

    Objects with identity columns (such as auto-incrementing primary keys) are fully supported.
    Smart DevOps will track row insertions, updates and eletions
    based on the identity column, ensuring precise version control.

8. **Integrator Objects**

    Smart DevOps also tracks all the changes made through integrator. 

    No extra configuration needed - as long as tracking is enabled for the related object, all integrator-related changes will be captured automatically.

## Limitations

While Smart DevOps provides robust tracking , there are some limitations to be aware of:

- **Commands Not Tracked**  
  Actions performed using the following MOCA commands are **not tracked**:
  - create record
  - change record
  - remove record

  These commands bypass the Smart DevOps tracking mechanism.

- **SQL-Based Changes Not Tracked**  
  Any data modifications made directly through **SQL queries** (e.g., INSERT, UPDATE, DELETE) are **not tracked** by Smart DevOps.


---

<br><br>


