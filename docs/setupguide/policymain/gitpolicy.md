# Policy setup for Version Control Systems
   To enable version control functionality in Smart DevOps, you must properly set up the related policies.
    These policies ensure that versioning features such as commit tracking, branching, and script integration work seamlessly within the Smart DevOps environment.

These settings are essential to connect your application with external version control tools and services like Git

You need to enable these policies:

1. **Enable Git as Version Control System**

    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | VERSION-CONTROL-SYSTEM   | GIT    |

      Use case: Sets Git as the backend for version control.

2. **Set Git Repository**
    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-REPO   |  REPOSITORYNAME  

    Use case: Specifies the remote Git repository where changes will be committed.

    Replace the REPOSITORYNAME in rtsrt1 with your own repository name where changes will be committed.

3. **Set Active Git Branch**	

    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-ACTIVE-BRANCH   | BRANCHNAME    |

    Use case: Defines the current working branch used for commits.

    Replace the BRANCHNAME in rtsrt1 with your own branch name used for commits.

4. **Set Main Git Branch**
    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-MAIN-BRANCH   | BRANCHNAME    |

    Use case: Identifies the main (default) branch of the repository.

    Replace the BRANCHNAME in rtsrt1 with your own branch name.

5. **Set Git Executable Path**

    | `polcod`                 | `polvar` | `polval`             | `rtstr1`              |
    |--------------------------|----------|----------------------|------------------------|
    | USR-OSSI-VERSION-CONTROL             | SETUP    | GIT-EXEC-PATH   | PATH    |

    Use case: Points to the executable path of the Git CLI used by the system.
    
    Replace PATH in rtsrt1 with executable directory path of your system for GIT.

