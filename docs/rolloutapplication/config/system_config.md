# System Configuration

The System Configuration tab allows users to define platform-level settings that influence how rollout packages behave and are processed across environments.

To **configure system** follow the steps:
 
-  Click on Settings from the sidebar.
- Navigate to the Rollout Package Configuration screen.

    <div style="text-align: left;">
      <img src="./assets/system.png"
       alt="undirectedmenu"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
      </div>


**1. OS_PLATFORM**

Defines the operating system on which the system is running. This value can be used to tailor commands or scripts for the appropriate environment.

- **Options:** `linux`, `windows`
- **Example:** `linux`

**2. DOWNLOAD_PLATFORM**

Specifies the target platform for which the rollout packages should be downloaded or generated.

- **Options:** `linux`, `windows`
- **Example:** `linux`

**3. Date_Format**

Sets the preferred date format for timestamps used across the application.

- **Format Pattern:** Should follow common date format conventions
- **Example:** `DD/MM/YYYY` or `MM-DD-YYYY`

**4. RELEASE_NOTE_FILE**

Indicates whether a release note file is required for each rollout.

- **Options:**
  - `yes`: A release note must accompany the rollout.
  - `no`: Release note is optional.

**5. Version**

Defines the current version of the system configuration or rollout process.

**6. Submit Changes**

Click the **Submit** button to save the system configuration settings.

---
<br>