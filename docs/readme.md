 # Overview
 
This documentation covers Important components designed to streamline and manage the development and deployment lifecycle within the Blue Yonder WMS ecosystem:
 **Issue assignment** and the **Rollout Application**. Although these tools can also work as standalone where they serve distinct roles:

##  Issue Assignment
 
**Issue Assignment** is a BY portal–integrated solution for managing and tracking changes in the BY-WMS environment. It streamlines the entire change management process—from initial configuration to deployment—while ensuring traceability, repeatability, and minimal manual effort.
 
### Key Highlights
- Track and manage all changes in the BY-WMS environment.
- Simplify the complexity of the BY data model for developers and functional users.
- Maintain a consistent rollout process using standard BY methodology.
- Integrate seamlessly with tools like JIRA and Git.
- Ensure complete traceability via OSSI logs for overridden tables.
 
[View Issue Assignment Documentation](./setupguide/setupguide.md)
 
## Rollout Application
 
The **Rollout Application** is a web-based tool that connects Azure DevOps (for issue management) with Git (for version control). It enables users to generate rollout packages based on Azure issue IDs, significantly reducing the time and effort required for deployment.
 
### Key Highlights
- Generate `.zip` or `.tar` rollout packages automatically.
- Fetch and package affected files from Git based on Azure issues.
- Eliminate manual tracking and reduce rollout errors.
- Improve deployment speed, accuracy, and efficiency.

[View Rollout Application Documentation](./rolloutapplication/overview.md)