---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC, help, support

subcollection: security-services

---

{{site.data.keyword.attribute-definition-list}}

# Getting help and support for the {{site.data.keyword.name-da}} deployable architectures
{: #help-support}

If you experience an issue or have questions when you deploy your {{site.data.keyword.name-da}} deployable architecture, you can use the following resources before you open a support case.
{: shortdesc}


- Review the [troubleshooting documentation](/docs/security-services?topic=security-services-ts-secrets-mgr-trial) to troubleshoot and resolve common issues.
- ![{{site.data.keyword.cloud_notm}} icon](../icons/ibm-cloud-16.svg "IBM Cloud icon") Check the status of the {{site.data.keyword.cloud_notm}} platform and resources by going to the [Status page](https://cloud.ibm.com/status){: external}.
- ![GitHub icon](../icons/logo-github-16.svg "GitHub icon") Review the [GitHub issues](https://github.com/terraform-ibm-modules/stack-ibm-core-security-services/issues){: external} to see whether other users experienced the same problem.




If you still can't resolve the problem, you can open a support case. For more information, see [Creating support cases](/docs/get-support?topic=get-support-open-case). If you're looking to provide feedback, see [Submitting feedback](/docs/overview?topic=overview-feedback).

## Providing support case details
{: #support-case-details}

To ensure that the support team can start investigating your case to provide a timely resolution, you must include details from two logs from your failed deployment.

1.  In your project, go to the needs attention widget on the **Overview** tab and click the message to view more information about the issue.
1.  Provide the member configuration name, source URL, and source release, and folder from the {{site.data.keyword.bpshort}} log:
    1.  In the log file, find the architecture information. In the following example, you see the `Related Workspace`, `sourcerelease`, and `sourceurl`:

        ```sh
        2023/04/06 18:11:43 Related Workspace: name=2 - Observability, sourcerelease=(1.0.0), sourceurl=, folder=folder=terraform-ibm-kms-all-inclusive-4.8.5/solutions/standard
        ```
        {: screen}

    1.  Copy the architecture information and paste it into the case details.

## Routing your support case
{: #support-case-routing}

To route your support case correctly to speed up resolution, select the applicable product when you open the case.

### Routing when you can't deploy successfully
{: #support-routing-no-deploy}

If you can't deploy your deployable architecture, open a support case with the most likely cause of the issue:

- If you identified the member configuration that you think is causing the error from the {{site.data.keyword.bpshort}} log, use the name of that configuration as the product name in the case.
- If you can't identify the error from the {{site.data.keyword.bpshort}} log, use the name of the deployable architecture as it is listed in the IBM Cloud catalog.

### Routing when you deployed successfully
{: #support-routing-deploy}

If you successfully deployed, yet have an issue with a service in the deployable architecture, open a support case and use the name of that service.
