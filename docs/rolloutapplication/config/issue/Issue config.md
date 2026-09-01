# Issue Management Provider

The Issue Management Provider screen connects Rollout to your issue tracking system so rollout metadata, bug references, and version categories stay aligned with your delivery workflow.

The current Issue Management wizard shows **Jira**, **Bugzilla**, and **Azure DevOps** provider options. If you need to configure a Git-based repository connection, use the **Version Control** configuration screens instead of Issue Management.

## Open Issue Management

1. Go to **Settings** from the left navigation.
2. Open **Issue Management**.
3. On the view screen, review the current configuration details: `Provider`, `Base URI`, `API Version`, `Auth Type`, `Username`, `Sync Interval`, and `Project Category`.
4. Use **Test Connection** to validate the current setup, or click **Edit Configuration** to update it through the guided wizard.

![Issue Management view mode showing the current Azure DevOps provider configuration](./assets/issue-management-provider-view-mode.png)

## Configure Issue Management Providers

1. Click **Edit Configuration**.
2. In **Step 1 - Choose a provider**, select the issue tracking system your team uses.
3. Continue through the provider-specific setup flow below.

Provider-specific setup guides:
- [Jira Integration Setup](/rolloutapplication/config/issue/jira.md)
- [Bugzilla Integration Setup](/rolloutapplication/config/issue/bugzilla.md)
- [Azure Integration Setup](/rolloutapplication/config/issue/azure.md)

### Jira

1. In **Step 1 - Choose a provider**, select **Jira** and click **Continue**.

![Jira selected in Step 1 of the Issue Management provider wizard](./assets/issue-management-provider-select-jira.png)

2. In **Step 2 - Connection details**, review the **Jira REST API** option, choose the supported API version shown in the UI (`v2` or `v3`), enter the Jira **Base URI**, and use **Use default URL** if you want to restore the default format. Click **Continue** when the connection details are correct.

![Jira connection details step showing the Jira REST API version toggle and base URI field](./assets/issue-management-provider-jira-connection-details.png)

3. In **Step 3 - Configure connection**, choose the authentication type shown for your environment, then complete `Authentication Type`, `Username`, `Password`, `Sync Interval`, and `Project Category`. Click **Continue** after the form is complete.

![Configure connection step showing authentication, credentials, sync interval, and project category fields](./assets/issue-management-provider-jira-configure-connection.png)

4. In **Step 4 - Review & save**, confirm the Jira settings, optionally click **Test Connection**, and then click **Save Configuration**.

![Jira review and save step with Test Connection and Save Configuration actions](./assets/issue-management-provider-jira-review-save.png)

### Bugzilla

1. In **Step 1 - Choose a provider**, select **Bugzilla** and click **Continue**.

![Bugzilla selected in Step 1 of the Issue Management provider wizard](./assets/issue-management-provider-select-bugzilla.png)

2. In **Step 2 - Connection details**, review the **Bugzilla REST API** option, confirm the compatible API version badge (`v1`), enter the Bugzilla **Base URI**, and use **Use default URL** if needed. Click **Continue** to move to the next step.

![Bugzilla connection details step showing the REST API version and base URI field](./assets/issue-management-provider-bugzilla-connection-details.png)

3. In **Step 3 - Configure connection**, complete the Bugzilla configuration fields shown in the form. The current UI includes `Authentication Type`, `Username`, `Password`, `Sync Interval`, and `Project Category`.

![Bugzilla configure connection step with example values filled in](./assets/issue-management-provider-bugzilla-configure-connection.png)

4. In **Step 4 - Review & save**, verify the Bugzilla provider details, run **Test Connection** if required, and click **Save Configuration** to finish.

![Bugzilla review and save step showing the final configuration summary](./assets/issue-management-provider-bugzilla-review-save.png)

### Azure DevOps

1. In **Step 1 - Choose a provider**, select **Azure DevOps** and click **Continue**.

![Azure DevOps selected in Step 1 of the Issue Management provider wizard](./assets/issue-management-provider-select-azure-devops.png)

2. In **Step 2 - Connection details**, review the **Azure DevOps API** option, confirm the compatible API version badge (`v5`), enter the Azure DevOps **Base URI**, and use **Use default URL** when you want to restore the default value. Click **Continue** to proceed.

![Azure DevOps connection details step showing the API version badge and base URI field](./assets/issue-management-provider-azure-connection-details.png)

3. In **Step 3 - Configure connection**, complete the same connection form used by the wizard for credentials and sync settings. Fill in `Authentication Type`, `Username`, `Password`, `Sync Interval`, and `Project Category`, then click **Continue**.

![Configure connection step used to enter authentication and sync settings](./assets/issue-management-provider-azure-configure-connection.png)

4. In **Step 4 - Review & save**, confirm the Azure DevOps settings, optionally use **Test Connection**, and click **Save Configuration**.

![Azure DevOps review and save step showing the final provider summary](./assets/issue-management-provider-azure-review-save.png)

---
<br>
