---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC

subcollection: security-services

---

{{site.data.keyword.attribute-definition-list}}

# Updating to a new deployable architecture version
{: #update-css}

When you are notified about new versions of your deployable architecture and want to update to the new version, edit the configuration.
{: shortdesc}

You can monitor and address other project lifecycle events from the Needs attention widget. For more information, see [Viewing needs attention items](/docs/secure-enterprise?topic=secure-enterprise-needs-attention-projects).
{: tip}

A good practice is to deploy new versions in your testing environment first to check for issues. Then, deploy to your production environment. You might also want to deploy the new version to a single region first to check for issues before you deploy to all regions.

To update your configuration, complete the following steps:

1.  From the projects list, select a project.
1.  Go to the **Configurations** tab, and select a deployable architecture configuration.
1.  Click **Edit**.
1.  In the Select inputs section, use the **Version** menu to select the new version of the deployable architecture.
1.  Click **Save**.
1.  [Validate and deploy the architecture](/docs/security-services?topic=security-services-deploy-css#deploy-validate).
