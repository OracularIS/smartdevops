# Rollout Package Configuration

This section defines the parameters used to generate and manage rollout packages. A rollout package contains source code changes bundled for deployment.

To **configure rollout package integration** follow the steps:
 
- Click on Settings from the sidebar.
- Navigate to the Rollout Package Configuration screen.

    <div style="text-align: left;">
      <img src="./assets/rollout.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


**1. Define Rollout Naming Convention**

**ROLLOUT_NAME**: Template string that defines the format of the rollout package name.

Supported variables:
- `{PROJECT}` – Project identifier
- `{VERSION}` – Version number
- `{BUGID}` – Bug or issue ID

**Example:**

```
ROLLOUT-OSSI-{PROJECT}-{VERSION}-{BUGID} 
→ ROLLOUT-OSSI-APP01-1.0.5-12345
```

**2. Set Destination Path**

**ROLLOUT_DESTINATION_PATH**: Directory path where the final rollout package will be saved.

**Example:**

```
/var/www/html/backend/rollout_dir/rollouts
```

**3. Define Source Path**

**ROLLOUT_SRC_PATH**: Base directory containing the repositories or source files that are used for packaging.

**Example:**

```
/var/www/html/backend/rollout_dir/rollouts
```

> Ensure both the source and destination paths are accessible by the application and have appropriate read/write permissions.

**4. Save Configuration**

Click the **Submit** button to store the rollout configuration.

---
<br>