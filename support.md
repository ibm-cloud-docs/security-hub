---

copyright:
  years: 2024
lastupdated: "2025-02-10"

keywords: security hub, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Getting help and support for the Essential Security and Observability Services deployable architecture
{: #help-support}

If you experience an issue or have questions when you deploy the Essential Security and Observability Services deployable architecture, you can use the following resources before you open a support case.
{: shortdesc}


- Review the [troubleshooting documentation](/docs/security-hub?topic=security-hub-ts-secrets-mgr-trial) to troubleshoot and resolve common issues.
- Review the [FAQs](/docs/security-hub?topic=security-hub-faqs).
- ![{{site.data.keyword.cloud_notm}} icon](../icons/ibm-cloud-16.svg "IBM Cloud icon") Check the status of the {{site.data.keyword.cloud_notm}} platform and resources by going to the [Status page](https://cloud.ibm.com/status){: external}.
- ![GitHub icon](../icons/logo-github-16.svg "GitHub icon") Review the [GitHub issues](https://github.com/terraform-ibm-modules/stack-ibm-core-security-services/issues){: external} to see whether other users experienced the same problem.


If you are unable to resolve the issue, open a support case. For more information, see [Creating support cases](/docs/account?topic=account-open-case). If you're looking to provide feedback, see [Submitting feedback](/docs/overview?topic=overview-feedback).


## Providing support case details
{: #support-case-details}

To ensure that your case has a timely resolution, be sure to include the information found in the logs from your failed deployment so that we can begin investigating your case. To provide the logs, use the following steps.

1. In your project, go to the **Needs attention** widget on the **Overview** tab. Then, click the message to view more information about the issue.
1. Provide the member configuration name, source URL, source release, and folder from the {{site.data.keyword.bpshort}} log. It should look similar to the following example. 

   ```sh
   2023/04/06 18:11:43 Related Workspace: name=2 - Observability, sourcerelease=(1.0.0), sourceurl=, folder=folder=terraform-ibm-kms-all-inclusive-4.8.5/solutions/standard
   ```
   {: screen}

1. Copy the information and paste it into the case details.


## Routing your support case
{: #support-case-routing}

Depending on whether you were able to deploy the architecture, you provide different information for the product name in your case. 

If you are able to deploy the architecture, provide the name of the service that you believe is causing the issue that you are encountering. 

If you are unable to deploy the architecture and you're able to identify a likely reason, include your thoughts on what might be causing the problem. It is helpful if you can provide the name of that configuration as the product name for the case. If you are unable to narrow the cause of the issue to a specific service or configuration, provide the name of the deployable architecture.
