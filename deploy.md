---

copyright:
  years: 2024
lastupdated: "2024-10-14"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Deploying the architecture
{: #deploy-css}

To deploy the Essential Security and Observability Services deployable architecture, you can start from the {{site.data.keyword.cloud_notm}} catalog.
{: shortdesc}

## Before you begin
{: #deploy-before}

Before you get started, be sure that you have completed all of the prerequistes outlined in [Before you begin](/docs/security-hub?topic=security-hub-prereqs).

## Adding the architecture to a project
{: #deploy-details-deploy}

To deploy an architecture, you must add it to a project.

1. In the [{{site.data.keyword.cloud_notm}} catalog](/catalog#reference_architecture){: external}, search for the Essential Security and Observability Services deployable architecture.
1. Select the tile for the deployable architecture.
1. In the **Architecture** section, choose the latest product version.
1. Click **review deployment options**.
1. In the **Deployment options** section, select **Add to project**. Then, click **Add to project**.
1. Give your project a name, enter a descriptoin, and specify a configuration name.
1. Click **Create**.


## Configuring your stack
{: #deploy-configure}

To create a configuration, set your variables.

1. In the **Configure > Security** add the API that you previously identified as part of the prerequistes to select the authentication method that will be used to deploy your architecture.
1. In the **Configure > Security** > **Authentication** tab select the API key.
1. On the **Required** tab, enter the values for the following required fields.
   * Enter a prefix. A prefix is added to the beginning of the name of most of the resources that are created by the deployable architecture. The prefix helps to make sure that the resource names are unique and it helps to avoid naming clashes with other resources in the same account.
   * Select the region in which you want the resources created.
   * Provide the name of a resource group.
1. On the **Optional** tab, enter the values for the optional fields.
   * Select the pricing plans for {{site.data.keyword.secrets-manager_short}} and {{site.data.keyword.compliance_short}}. While these fields are optional, they are required if you are building the sample app.
1. Click **Save**. After the input values are validated, the button changes to **View stack configurations**.


## Validating and deploy the architecture
{: #deploy-validate}

You can deploy a stacked deployable architecture in two ways:

- By using **Auto-deploy**: The deployment method can be useful for demonstration and nonproduction environments. With auto-deploy, all the stack member configurations are validated and then approved and deployed.

    You can check the **Auto-deploy** setting for your project by clicking **Manage** > **Settings**. By turning on Auto-deploy, you enable the setting for all configurations in the project.
    {: tip}

- Individually by deploying each member configuration. The manual method is appropriate for projects that hold production environments. You can review the changes in each member configuration before the automation is run.

### Auto-deploying the architecture
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

The Essential Security and Observability Services deployable architecture is now deployed in the target account.

## Viewing the created resources
{: #deploy-view-resources}

When the architecture is finished deploying, the resources are available in your account. To view them, you can use the following steps. 

1. In the {{site.data.keyword.cloud_notm}} console, select **Resource list** from the navigation in your target account.
1. Select the resource group and region where the infrastructure was deployed by the architecture.
