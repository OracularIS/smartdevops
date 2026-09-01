# Bugzilla Integration Setup

This page explains how to configure **Bugzilla** as the Issue Management Provider in Rollout.

## Configuration Fields for Bugzilla

The current Bugzilla setup uses the following fields in the wizard:

| Field | Value |
| --- | --- |
| Provider | `Bugzilla` |
| API Version | `v1` |
| Base URI | `https://bugzilla.your-instance.com` |
| Authentication Type | `oAuthBasic` |
| Username | Bugzilla user account |
| Password | Bugzilla password or the credential required by your instance |
| Sync Interval | Set in minutes |
| Project Category | `fixVersion` or the matching Bugzilla version category used by your team |

The current Bugzilla wizard uses these fields across the connection details, authentication, and review steps.

## Step 1 - Choose a Provider

1. Open **Settings**.
2. Select **Issue Management**.
3. Click **Edit Configuration**.
4. In **Step 1 - Choose a provider**, select **Bugzilla** and click **Continue**.

![Bugzilla selected in the Issue Management provider wizard](./assets/issue-management-provider-select-bugzilla.png)

## Step 2 - Connection Details

In **Step 2 - Connection details**:

- Review the **Bugzilla REST API** connection type.
- Confirm the compatible API version badge, `v1`.
- Enter the Bugzilla **Base URI**.
- Use **Use default URL** if you need to restore the default value.
- Click **Continue** to proceed.

![Bugzilla connection details showing the REST API version and base URI field](./assets/issue-management-provider-bugzilla-connection-details.png)

## Step 3 - Configure Connection

In **Step 3 - Configure connection**:

- Confirm the authentication type shown in the current UI.
- Enter the Bugzilla `Username`.
- Enter the Bugzilla `Password`.
- Set the `Sync Interval` in minutes.
- Select the `Project Category` used by your Bugzilla setup.
- Click **Continue** after completing the form.

![Bugzilla configure connection step with credentials and project category values](./assets/issue-management-provider-bugzilla-configure-connection.png)

## Step 4 - Review & Save

In **Step 4 - Review & save**:

- Review `Provider`, `Base URI`, `API Version`, `Auth Type`, `Username`, `Sync Interval`, and `Project Category`.
- Click **Test Connection** if you want to validate the Bugzilla settings before saving.
- Click **Save Configuration** to complete the setup.

![Bugzilla review and save step showing the final configuration summary](./assets/issue-management-provider-bugzilla-review-save.png)

---
<br>
