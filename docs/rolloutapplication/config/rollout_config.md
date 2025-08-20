# Rollout Package Configuration

This section defines the parameters used to generate and manage rollout packages. A rollout package contains source code changes bundled for deployment.

## Configure rollout package integration

To configure rollout package integration follow the steps:
 
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

The table below outlines the required configuration fields for rollout package configuration.

<center>

| Field                     | Value                                                                                          |
|---------------------------|------------------------------------------------------------------------------------------------------|
| Rollout Name          | `ROLLOUT-OSSI-{PROJECT}-{VERSION}-{BUGID}` Example:  ROLLOUT-OSSI-APP01-1.0.5-12345   |
| Destination Path | /var/www/html/rollout_dir/rollouts                                        |
| Source Path      | /var/www/html/rollout_dir/repos  |

</center>

> 💡 **Tip:** Use the **suggestion button** to see recommended inputs and sample values for the field.  

---
<br>