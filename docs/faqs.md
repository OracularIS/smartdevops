# FAQs

+ **Question 1:** What is Smart DevOps? +

  SmartDevOps is a version control and deployment tool integrated with Blue Yonder (BY) environments. It helps track, manage, and rollout development changes safely and efficiently using policies, issue assignments, and control files.

+ **Question 2:** What tools or setup are required to use Smart DevOps? +

  To use Smart DevOps, you must have the MOCA Client installed and the OSSI Issue Assignment module configured in your BY environment. These are prerequisites for accessing and managing issues through Smart DevOps.

+ **Question 3:** How are changes tracked in Smart DevOps? +

  Smart DevOps tracks changes through issue assignments. Any modifications made using MOCA commands, the GUI, or integrator tools are logged against a specific issue ID. These changes can later be viewed or rolled out through the Smart DevOps platform.

+ **Question 4:** What types of changes does Smart DevOps track? +

  Smart DevOps tracks code changes (e.g., MOCA commands), data changes (via MOCA or portal), integrator changes (events, IFDS), and GUI-related changes. All tracked changes are linked to specific issues for easy review and deployment.

+ **Question 5:** How can I create a rollout using Smart DevOps? +

  To create a rollout, complete your changes, go to the OSSI Issue Assignment screen, and select the “Complete” option. Then enable the "Create Rollout" option before confirming with “OK.” This will generate the rollout package in the backend.

+ **Question 6:** Is it possible to commit changes without creating a rollout? +

  Yes when completing an issue, enable only the “commit” option if you do not wish to generate a rollout. This will save the changes to the version control system without creating a rollout package.

+ **Question 7:** Where can I view the changes tracked by Smart DevOps? +

  Tracked changes can be viewed from:
  - **MOCA Client** via logs or command history
  - **Fat Client** in the Issue Assignment screen under the relevant tabs
  - **Thin Client** (if integrated) showing logs and changes as per the configuration

+ **Question 8:** How do I disable tracking for specific fields or objects? +

  You can disable tracking by modifying the associated policy. For example, if you do not want to track changes to a description field in a table, disable the policy that governs tracking for that field.

  
---

<br><br>