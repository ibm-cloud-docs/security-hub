---

copyright:
  years: 2024
lastupdated: "2025-05-02"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Customizing your deployment
{: #customize-css}

You can customize the Essential Security and Observability Services deployable architecture in several different ways. The deployable architecture is configured to use specific services, but you are able to edit the configuration, remove specific members, or add members before deploying your architecture. Be sure to keep in mind that changing the members of an architecture might potentially change the use case.
{: shortdesc}

## Editing member configurations
{: #customize-edit-config}

Each member in the deployable architecture stack includes several input parameters that can be customized to your specific use case. To change the default value, you can edit the configuration. For example, you can determine whether the endpoint type is private or public. You can choose to reuse existing keys that you already have in {{site.data.keyword.keymanagementserviceshort}}. Or, you might fine-tune the parameters of some of the other services. 

To edit the member configuration, select **Edit** from the Options icon ![Options icon](../icons/action-menu-icon.svg "Options") in the member configuration row of your project.



## Managing inputs and outputs
{: #customize-manage-vars}

You can add and remove input and output variables that are available in the Essential Security and Observability Services deployable architecture by following these steps:

1.  In your project, click the **Configurations** tab.
1.  Select a member configuration.
1.  From the **Deployed details** window, you can promote any of the configuration inputs or outputs.


## Removing configurations
{: #customize-remove-config}

You can remove a member configuration from the stack that other configurations don't depend on. In the Essential Security and Observability Services deployable architecture, you can remove the configurations for the following services:

- {{site.data.keyword.compliance_short}}
- {{site.data.keyword.secrets-manager_short}}

To remove a member configuration, select **Remove from Stack** from the Options icon ![Options icon](../icons/action-menu-icon.svg "Options") in the member configuration row.
