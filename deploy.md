---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}
# Deploying the {{site.data.keyword.name-da}} deployable architecture
{: #deploy-css}

You can deploy a deployable architecture from the {{site.data.keyword.cloud_notm}} catalog.
{: shortdesc}

To deploy the {{site.data.keyword.name-da}} architecture through the {{site.data.keyword.cloud_notm}} catalog, follow these steps. If you want to update to a new version, see [Updating to a new deployable architecture version](/docs/security-services?topic=security-services-update-css).


Make sure that you comply with the prerequisites in the [planning](/docs/security-services?topic=security-services-prereqs) topic.
{: important}

## Step 1. Add the architecture to a project
{: #deploy-details-deploy}

1.  Go to the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external} and search for the {{site.data.keyword.name-da}} deployable architecture.
1.  Click the tile for the deployable architecture to open the details.
1.  Select the latest product version in the Architecture section.
1.  Click **Review deployment options**.
1.  Select the **Add to project** deployment type in **Deployment options**, and then click **Add to project**.

    For more information about the enterprise account structures, see the [Central administration account](/docs/enterprise-account-architecture?topic=enterprise-account-architecture-admin-hub-account) white paper.

    1.  Name your project, enter a description, and specify a configuration name.
    1.  Click **Create**.

## Step 2. Configure your stack
{: #deploy-configure}

Create your configuration by setting variables.

1.  From the **Security** panel, select the authentication method that you want to use to deploy your architecture.

    Add the API key that you identified in the [planning](/docs/security-services?topic=security-services-prereqs) topic.

1.  In the **Security** > **Authentication** tab in the **Configure** section, select the API key.

1.  Enter values for required fields from the **Required** tab.

    1.  Enter a prefix. This prefix is added to the beginning of the name of most resources that are created by the deployable architecture. The prefix helps to make sure that the resource names are unique, and it avoids clashes with other resources in the same account.
    1.  Select the region to create the resources, and provide a resource group name.
1.  Review values for optional fields from the **Optional** tab:

    1.  Select the pricing plans for {{site.data.keyword.secrets-manager_short}} and {{site.data.keyword.compliance_short}}. These fields are optional fields. However, they are required to build the sample app.
    1.  Review the other input variables.

1.  Click **Save**. After the input values are validated, the button changes to **View stack configurations**.

## Step 3. Validate and deploy the architecture
{: #deploy-validate}

You can deploy a stacked deployable architecture in two ways:

- By using **Auto-deploy**: The deployment method can be useful for demonstration and nonproduction environments. With auto-deploy, all the stack member configurations are validated and then approved and deployed.

    You can check the **Auto-deploy** setting for your project by clicking **Manage** > **Settings**. By turning on Auto-deploy, you enable the setting for all configurations in the project.
    {: tip}

- Individually by deploying each member configuration. The manual method is appropriate for projects that hold production environments. You can review the changes in each member configuration before the automation is run.

### Deploying the architecture with Auto-deploy
{: #deploy-auto}

1.  Click the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") next to **View stack configurations** and click **Validate**.

    If the **Auto-deploy** setting is off in your project, only member configurations that are ready are validated.

### Deploying each member configuration
{: #deploy-manual}

1.  In your project, click the **Configurations** tab.

    If the first member configuration of the stack (`1a - Key management`) is not marked as **Ready to validate**, refresh the page in your browser.
1.  Click **Validate** in **Draft status** in the `1a - Key management` row.
1.  Approve the configuration and click **Deploy** after validation successfully completes.
1.  After you deploy the initial member configuration, you can validate and deploy the remaining member configuration at the same time. Repeat these deployment steps for each member configuration in the architecture.

The {{site.data.keyword.name-da}} deployable architecture is now deployed in the target account.

## Viewing resources created by the deployable architecture
{: #deploy-view-resources}

View the resources created by the deployable architecture.

1.  In the {{site.data.keyword.cloud_notm}} console, click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Resource list** in the target account.
1.  Choose the resource group and region where the infrastructure was deployed.
