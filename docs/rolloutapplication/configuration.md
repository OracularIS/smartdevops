## Rollout Package Configuration

This section defines the parameters used to generate and manage rollout packages. A rollout package contains source code changes bundled for deployment.

### 1. Define Rollout Naming Convention

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

### 2. Set Destination Path

**ROLLOUT_DESTINATION_PATH**: Directory path where the final rollout package will be saved.

**Example:**

```
/var/www/html/rollout_dir/rollouts
```

### 3. Define Source Path

**ROLLOUT_SRC_PATH**: Base directory containing the repositories or source files that are used for packaging.

**Example:**

```
/var/www/html/rollout_dir/repos
```

> Ensure both the source and destination paths are accessible by the application and have appropriate read/write permissions.

### 4. Save Configuration

Click the **Submit** button to store the rollout configuration.

---

## System Configuration

The System Configuration tab allows users to define platform-level settings that influence how rollout packages behave and are processed across environments.

### 1. OS_PLATFORM

Defines the operating system on which the system is running. This value can be used to tailor commands or scripts for the appropriate environment.

- **Options:** `linux`, `windows`
- **Example:** `linux`

### 2. DOWNLOAD_PLATFORM

Specifies the target platform for which the rollout packages should be downloaded or generated.

- **Options:** `linux`, `windows`
- **Example:** `linux`

### 3. Date_Format

Sets the preferred date format for timestamps used across the application.

- **Format Pattern:** Should follow common date format conventions
- **Example:** `DD/MM/YYYY` or `MM-DD-YYYY`

### 4. RELEASE_NOTE_FILE

Indicates whether a release note file is required for each rollout.

- **Options:**
  - `yes`: A release note must accompany the rollout.
  - `no`: Release note is optional.

### 5. Version

Defines the current version of the system configuration or rollout process.

### 6. Submit Changes

Click the **Submit** button to save the system configuration settings.

---

## AUTH Configuration

This section allows you to enable or disable the different authentication mechanisms:

- **AUTH Database Configuration**: Enables authentication using credentials stored in a local database.
- **AUTH LDAP Configuration**: Enables authentication using LDAP (Lightweight Directory Access Protocol).
- **Login With Azure Configuration**: Enables Microsoft Azure Active Directory login.
- **Login With Google Configuration**: Enables Google OAuth2 login.

---

### AUTH Database Configuration

Used when AUTH Database Configuration is enabled.

- **SUPER_USER**: This is the default administrator username for the system when using database-based login.

---

### Login With Azure Configuration

Used when Login with Azure Configuration is enabled.

- **AZURE_CLIENT_ID**: The Client ID obtained from Azure Active Directory for your application.
- **AZURE_CLIENT_SECRET**: The secret key associated with the Azure Client ID.
- **AZURE_TENANT_ID**: The Azure Directory (tenant) ID for your organization.
- **AZURE_REDIRECT_URI**: The URI Azure will redirect users to after a successful login.

**Example:**

```
http://localhost:8081/social/login/callback
```

> Make sure this URI matches the one registered in your Azure AD application.

---

### Login With Google Configuration

Used when Login With Google Configuration is enabled.

- **GOOGLE_CLIENT_ID**: The Client ID obtained from Google Cloud Console for your application.
- **GOOGLE_CLIENT_SECRET**: The secret key associated with the Google Client ID.
- **GOOGLE_REDIRECT_URL**: The URI Google will redirect users to after successful login.

**Example:**

```
http://localhost:8081/social/login/callback
```