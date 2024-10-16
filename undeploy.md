---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Undeploying the deployable architecture
{: #undeploy}

Delete the stacked deployable architecture and all associated infrastructure resources.
{: shortdesc}

To undeploy the infrastructure created by the deployable architecture, complete the following steps:

You can also [delete the project](/docs/secure-enterprise?topic=secure-enterprise-delete-project) to delete all member configurations if you do not want to delete member configurations one by one.
{: tip}

1.  [Install or update](/docs/cli?topic=cli-getting-started) the {{site.data.keyword.cloud_notm}} CLI.
1.  From the project dashboard, select the **Configurations** tab.
1.  Undeploy the member configurations in the project:

    1.  Undeploy the `4b - Secrets Manager` configuration member. Wait for the undeploy to complete.
    1.  Undeploy the next member configuration. Wait for the undeploy to complete.
    1.  Continue to undeploy the configurations, but wait for each undeploy to complete before you undeploy the next.

1.  Delete your project.

    After all configurations are undeployed, you can delete the project.
