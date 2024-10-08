---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC

subcollection: security-services

---

{{site.data.keyword.attribute-definition-list}}

# Customization options
{: #customize-css}

The {{site.data.keyword.name-da}} deployable architecture supports several customization options. These are some common options.
{: shortdesc}

## Editing member configurations
{: #customize-edit-config}

Each member configuration in the deployable architecture stacks includes a large number of input parameters. You can edit the configuration to change the default values.

For example, by editing the member configuration, you can accomplish these things:

- Configure the endpoint type as private or public.
- Reuse existing {{site.data.keyword.keymanagementserviceshort}} keys.
- Tune the parameters of individual services.

To edit the member configuration, select **Edit** from the Options icon ![Options icon](../icons/action-menu-icon.svg "Options") in the member configuration row.

## Removing configurations
{: #customize-remove-config}

You can remove a member configuration from the stack that other configurations don't depend on.

In the {{site.data.keyword.name-da}} deployable architecture, you can remove the following configurations:

- {{site.data.keyword.compliance_short}}
- {{site.data.keyword.secrets-manager_short}}

To remove a member configuration, select **Remove from Stack** from the Options icon ![Options icon](../icons/action-menu-icon.svg "Options") in the member configuration row.

## Managing inputs and outputs
{: #customize-manage-vars}

You can add and remove input and output variables that are available in the {{site.data.keyword.name-da}} deployable architecture by following these steps:

1.  In your project, click the **Configurations** tab.
1.  Select a member configuration.
1.  From the deployed details window, you can promote any of the configuration inputs or outputs.
