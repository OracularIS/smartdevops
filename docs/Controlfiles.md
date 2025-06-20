## Structure of Control Files

Control files are essentially the brain behind the CSV files.  
They instruct the system on **how to process the data**, define **which commands to execute**, and determine **where and how** the changes should be applied.



### Regular Control Files

- These control files are used for **create** and **update** operations.
- They reside in the **load directory** within the data folder.
- Each control file corresponds to a specific functional area and is responsible for processing the CSV data using **standard MOCA commands** (e.g., Create Movement Zone, Change Category, etc.)

#### Key Characteristics:
- Located in: **.../load/**
- Operates on: Insert / Update logic
- Purpose: Safely load data into the target environment using business logic

### Delete Control Files

- These files are responsible for **removal operations**.
- Unlike regular control files, delete control files are **stored outside** the load directory.
- They are placed in a special folder: **usr_ossi_Delete**
- These control files execute **remove MOCA commands** like Remove Movement Zone, Remove Category, etc.
- This separation ensures deletion logic is **clearly isolated**, reducing risk of unintentional data loss.

#### Key Characteristics:
- Located in: **.../usr_ossi_Delete/**
- Operates on: Deletion logic only
- Purpose: Safely remove records while preserving referential integrity
---

<br><br>
