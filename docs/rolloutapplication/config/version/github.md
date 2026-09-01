# Configure GitHub Integration

This page explains how to configure **GitHub** in the current Version Control Provider wizard.

## Configuration Fields for GitHub

The current GitHub setup uses the following values across the wizard:

| Field | Value |
| --- | --- |
| VCS Type | `Git` |
| Provider | `GitHub` |
| API Version | `v3` |
| Base URI | `https://api.github.com/` |
| Username | GitHub user account |
| Password / Token | GitHub personal access token |
| Workspace / Org | Repository owner, organization, or workspace value used by your setup |
| Default Branch | Repository default branch, such as `main` |
| Multi-File Path | Repository file path or folder name, such as `RPWEB` |

## Step 1 - VCS Type

1. Open **Settings**.
2. Select **Version Control**.
3. Click **Edit**.
4. In **Step 1 - VCS Type**, choose **Git** and click **Continue**.

## Step 2 - Provider

1. In **Step 2 - Provider**, select **GitHub** from the available Git hosting providers.
2. Click **Continue** to move to the API version step.

The current Provider step for Git-based integrations shows the available hosting options before you continue with the GitHub-specific API version and repository settings.
![Step 2 of the Version Control wizard showing GitHub selected](./assets/version-control-step-2-provider-github-selected.png)

## Step 3 - API Version

In **Step 3 - API Version**:

- Review the GitHub API version options.
- The current UI shows `v3`.
- The screen marks it as the recommended option.
- Click **Continue** after confirming the version.

![GitHub API Version step showing the recommended v3 option](./assets/version-control-step-3-github-api-version.png)

## Step 4 - Configuration

In **Step 4 - Configuration**, enter the repository connection values shown in the current UI:

- `Base URI`
- `Username`
- `Password / Token`
- `Workspace / Org`
- `Default Branch`
- `Multi-File Path`

Click **Continue** after completing the form.

![GitHub configuration step showing the base URI, token, and repository fields](./assets/version-control-step-4-github-configuration.png)

## Step 5 - Review & Save

In **Step 5 - Review & Save**:

- Review the selected provider, API version, base URI, username state, workspace or org value, default branch, and multi-file path.
- Use **Test Connection** if you want to validate the GitHub connection before saving.
- Click **Save Configuration** to complete the setup.

![GitHub review and save step showing the final configuration summary](./assets/version-control-step-5-github-review-save.png)

---
<br>
