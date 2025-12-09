# Rollout Application Flow

Learn how to configure and use the Rollout Application to efficiently manage rollouts and track changes.

## 1. Configure the Rollout Application

Before using the application, configure the following providers:

- **Issue Management Provider**
- **Version Control Provider**

Once configured, the Dashboard will display all available projects.

![Dashboard Image](./assets/Rolloutdashboardb.png)

## 2. Repository Setup

### 2.1 Create or Use an Existing Repository

- **New Repo:** Create a new repository in your version control system.
- **Existing Repo:** Ensure you have access to configure webhooks.

### 2.2 Configure Webhook

1. Go to **Repository Settings → Webhooks**.
2. Enable the **Push Event**.
3. Set the Webhook URL to:

```
{base_url_backend}/api/getWebhookData
```

![Webhook Configuration Page](./assets/bitbucketWebhook.png)

## 3. Work on Your Local Machine

### 3.1 Clone the Repository

```bash
git clone <repository_url>
```

### 3.2 Create and Checkout a New Branch

```bash
git checkout -b feature/your-feature-name
```

### 3.3 Make Changes

- Add or modify files according to your requirements.

### 3.4 Commit Changes

- Commit message format:

```
issue-number issue-description
```

- Example:

```
BY-123 Update user commands
```

### 3.5 Create Pull Request

1. Push your branch to the remote repository.
2. Create a Pull Request (PR) and merge it into the **main branch** after approval.

## 4. Verify Changes

After merging the PR, your changes will appear in the **Affected Files** page:

- URL: `{base_url_frontend}/searchaffectedfiles`
- Or navigate via **Utilities → Affected Files**.

![Affected Files Page](./assets/rollout_affected_files.png)

## 5. Create a Rollout

### 5.1 Select Project & Version

1. Navigate to the **Projects** screen.
2. Select the desired **Project** and **Version**.

![Select Project/Version Page](./assets/rollout_select_project_version.png)

### 5.2 Create Rollout

1. Enter or select your **Bug ID** from the Bug List.
2. Click **Create Rollout**.

![Create Rollout Page](./assets/create_rollout.png)

### 5.3 Download Rollout

- If successful, a popup will appear allowing you to **download the rollout**.

## Tips & Best Practices

- Use descriptive commit messages linking to the issue number.
- Verify webhook configuration to avoid missing commits.
- Keep branches small and focused for easier pull requests and rollouts.
- Use the Affected Files page to double-check changes before creating a rollout.

