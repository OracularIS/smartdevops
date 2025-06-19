# Setup for Version Control Systems
   To enable version control functionality in Smart DevOps, you must properly set up the related policies.
    These policies ensure that versioning features such as commit tracking, branching, and script integration work seamlessly within the Smart DevOps environment.

### Git Repoitory Setup
GIT repository should be setup such that it has the same overall directory structure as our LES folder.  In order to represent the GIT information below we will need following information
| `Concept`         | `Example`                | `Comments`                            | 
|-------------------|--------------------------|---------------------------------------|
| Name of the repo  | bytest                   | Each repo has a specific name         |
| Base URL for GIT  | `bitbucket.org/smart-is` | If you navigate to your GIT repo in browser, this is path before repo name |
| Name of main branch | `main`                 | Defined when creating repo.  Some use `master` as well.  |

Within the branch, then you should have the same structure as LES, so I should see folders like:
- bin
- src
- client
- etc

### Git Users
All BY users that need the ability to check in must be users in GIT.  Furthermore, they should generate a token for themselves as that is needed during check in.  Both GITHUB and BitBucket support the conncept of these tokens.  During check in, users provide the git credentials.

### Git Integration Concepts
The users develop in a common environment that is shared with other users.  Typically that implies
* Code is maintained in a common LES folder
* Integrations are in a common environment via BY fat client
* Setup is maintained in a common environment using BY fat or thin client

This is not how GIT is typically used.  In typical cases, developers have a complete isolation for the environment.  That setup implies too much overhead hence we typically follow above paradigm.  
But to work with GIT, we have a concept of a GIT sandbox **on the server**.  Decide on any folder on the BY MOCA server as the home folder for all git sandboxes.  So lets say we decide on `c:\BY\gitsbx`.  Per our concepts we will have following sub-folders:

- BY User Id
   - GIT Repo
      - Main Branch for the environment

### Recommended GIT Check in Flow
The Smart IS solution supports following GIT flow:
* Users assign themselves to an issue.  In the issue id, they specify the Jira# (or the issue id of another system).
* They make chaneges to source code (via Smart MOCA Client) or any other changes that are tracked
* Users complete the issue.  In the complete dialog they provide:
   * GIT usrename
   * GIT password (This is the token they created earlier)
   * Optionally provide a comment
   * **Do not specify a branch explicitly**
The system will proceeed as follows
1. If the user does not have the repository cloned, do that in the sandbox on the server for the user (see polval GIT-SANDBOX-ROOT below).
2. In that sandbox, create a branch named per policy expresson listed below (polval GIT-FEATURE-BRANCH-EXPR).  This will typically be `feature/<issue id in jira>`.
3. Do a pull to refresh it for the main branch changes. 
4. Go through all objects (files, data, or integrations).  If it is data or integration, it will create a file for that data.
5. Copy the file to corresponding location in the sandbox and do a "git add" on it as well.
6. Then at the end do "commit" and "push" for all affected files.  We will pass in the issue id and the comment provided by the user (conctenated) as a commit message.

Smart IS Git Integration ends at this point.  Users can then create a "pull request" and request "review" per their policies.

### Git Integration Policy Setup

These settings are essential to connect your application with external version control tools and services like Git.  These policies have polcod of USR-OSSI-VERSION-CONTROL, polvar of SETUP

| `polval`                 | `Set`    | `Value`              | `Comments`                       | `Example`            |
|--------------------------|----------|----------------------|----------------------------------|----------------------|
| VERSION-CONTROL-SYSTEM   | rtstr1   | git                  | This is the only supported value | git                  |
| GIT-REPO                 | rtstr1   | Name of the repo     | This is the name                 | bytest               |
| GIT-BASE-URL             | rtstr1   | URL                  | Base url of git repo | bitbucket.org/smart-is           |
| GIT-MAIN-WORK-BRANCH     | rtstr1   | name of the branch   | This is the branch which has code for env | main        |
| GIT-ACTIVE-BRANCH        | rtstr1   | branch for check in  | We typically create branch on the fly so not needed |   |
| GIT-CKIN-EXPLICIT-BRANCH-ALLOWED | rtnum1 | 0              | can we pass branch explicitly during check in. | 0      |
| GIT-SANDBOX-ROOT         | rtstr1   | MOCA expression      | Resolves to path on server for the user sandbox | See below |
| GIT-REMOVE-SUPPORTED     | rtnum1   | 1                    | Do we support remove operation 1 for yes | 1            |
| GIT-COMMIT-MESSAGE-SEP   | rtstr1   | _Value or blank_     | Delimiter for issue id if multple  | If multiple |
| GIT-FEATURE-BRANCH-EXPR  | rtstr1   | MOA Expression       | To create branch based on issue   | See below           |
| GIT-EXE-PATH             | rtstr1   | Path                 | Path to git appliation     | C:\PROGRA~1\Git\bin\git.exe|
| GIT-DO-PUSH              | rtstr1   | 1                    | Do we push on commit? 1 or 0 | 1                        |
| GIT-CKIN-SCRIPT          | rtstr1   | Script  | Name of script to do check in | smart_git_commit.sh                  |
| GIT-CKIN-SCRIPT-SHELL| rtstr1 | Path|This is the path to shell that runs check in|`"C:\Program Files\Git\bin\bash.exe" -c`|
| GIT-CREATE-BRANCH-SCRIPT-PARAM-QUOTE-CHAR|rtstr1,rtstr2|values|parameters within rtstr1.rtstr2 is to escape|`'` and `\'`|
| GIT-CREATE-BRANCH-SCRIPT|rtstr1|Path to Script|Name of script tp create branch| /c/blah/scripts/smart_git_create_branch.sh |
| GIT-CREATE-BRANCH-SCRIPT-SHELL|rtstr1|Path|This is the path to shell|`"C:\Program Files\Git\bin\bash.exe" -c`|
| GIT-CREATE-BRANCH-SCRIPT-PARAM-QUOTE-CHAR|rtstr1,rtstr2|values|parameters within rtstr1.rtstr2 is to escape|`'` and `\'`|

Following polval allow multiple rows to be added.  We concatenate all rtstr1 ordered by srtseq
* GIT-SANDBOX-ROOT

User id is the logged in BY user id.  If we want to remap it for some reason, we look up the user id in policy polval USERID-MAP for rtstr1 of the BY logged in user and take rtstr2.  We filter for rows that have rtnum1=1

Note that in some cases the rtstr1 is an expression.  In those cases following variables are available:

| `Variable`               | `Logic`         | `Used By Polval`                 |
|--------------------------|-----------------|----------------------------------|
| uc_issue_id_for_branch   | If a single issue id, then it is that value.  If multiple, then last | GIT-FEATURE-BRANCH-EXPR |
| usr_id                   | BY user or mapped user | GIT-SANDBOX-ROOT          |
| uc_git_repo              | polval GIT-REPO | GIT-SANDBOX-ROOT                 |
| uc_main_work_dir         | polval GIT-MAIN-WORK-BRANCH | GIT-SANDBOX-ROOT     |

For example, the GIT-FEATURE-BRANCH-EXPR is typically `'feature/' || @uc_issue_id_for_branch`

GIT-SANDBOX-ROOT is typically `'E:\JDA\SMARTRP_WM20\gitsbx\'||@usr_id||'\'||@uc_git_repo||'\'||@uc_main_work_dir`
    
---

<br><br>

