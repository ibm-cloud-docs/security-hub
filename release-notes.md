---

copyright:
  years: 2024
lastupdated: "2024-10-15"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for the Essential Security and Observability Services deployable architecture
{: #css-relnotes}

Use these release notes to learn about the latest updates to the Essential Security and Observability Services deployable architecture. The entries are grouped by date.
{: shortdesc}



## September 2024
{: #css-2024-09}

### 6 September 2024
{: #css-sep-0624}
{: release-note}

Version 1.4.1 of the {{site.data.keyword.name-da}} deployable architecture is available
:   The {{site.data.keyword.name-da}} deployable architecture version 1.4.1 [is released](/catalog#deployable_architecture){: external}.

    - When you upgrade, all deployable architecture members are updated to their latest versions.
    - Adds the `existing_en_instance_crn` input variable to specify an existing {{site.data.keyword.en_short}} instance.
    - Fixes an issue deploying the `4a - Security and Compliance Center` member with the profile attachment.

        If you received the `CreateAttachmentWithContext failed` error in version 1.3.1 and you removed the attachment as a workaround, follow these steps to add back the profile attachment:

        1.  Upgrade to version 1.4.1 or later.
        1.  In the {{site.data.keyword.cloud_notm}} console, click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Projects**.
        1.  Click the project with the stacked deployable architecture that you want to update.
        1.  Click the **Configurations** tab.
        1.  In the row for the member configuration named `4a - Security and Compliance Center`, click the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") and select **Edit**.
        1.  Click the **Optional** tab in the **Configure** section.
        1.  Find the **profile_attachments** input variable and click the **Edit** icon ![Edit icon](../icons/edit-tagging.svg "Edit").
        1.  Replace the empty list in the array with the following profile name:

            ```json
            [
              "IBM Cloud Framework for Financial Services"
            ]
            ```
            {: codeblock}

        1.  Click **Save**.
        1.  Follow the steps in [Step 3. Validate and deploy the architecture](/docs/security-services?topic=security-services-deploy-css#deploy-validate) to validate and deploy the updated deployable architecture.

## August 2024
{: #css-2024-08}

### 2 August 2024
{: #css-aug-0124}
{: release-note}

Version 1.3.1 of the {{site.data.keyword.name-da}} deployable architecture is available
:   The {{site.data.keyword.name-da}} deployable architecture version 1.3.1 [is released](/catalog#deployable_architecture){: external}.

    - Updates the {{site.data.keyword.secrets-manager_short}} member deployable architecture to version 1.17.1, which supports the use of `existing_secrets_manager_crn`.
    - Adds a `secret_manager_iam_engine_enabled` input variable to configure credentials for the {{site.data.keyword.secrets-manager_short}} IAM credentials engine. The default value is `false`.

## July 2024
{: #css-2024-07}

### 29 July 2024
{: #css-jul-2924}
{: release-note}

Version 1.2.1 of the {{site.data.keyword.name-da}} deployable architecture is available
:   The {{site.data.keyword.name-da}} deployable architecture version 1.2.1 [is released](/catalog#deployable_architecture){: external}.

     - When you upgrade, all deployable architecture members are updated to their latest versions.
     - A new `existing_kms_instance_crn` input variable adds support to use an existing key management service instance. By default, a new {{site.data.keyword.keymanagementserviceshort}} instance is created.
     - Fixes an issue in which activity tracking was not enabled for {{site.data.keyword.cos_full_notm}} buckets. By default, {{site.data.keyword.cos_short}} buckets that are created by the deployable architecture now have activity tracking enabled. When you upgrade, existing buckets are updated when you upgrade to this version.
     - Fixes an issue in which the {{site.data.keyword.en_short}} member created {{site.data.keyword.cos_short}} destinations instead of {{site.data.keyword.cos_short}} integrations that are needed to store failed events. When you upgrade, these destinations are destroyed.

### 1 July 2024
{: #css-jul-0124}
{: release-note}

Version 1.1.1 of the {{site.data.keyword.name-da}} deployable architecture is available
:   The {{site.data.keyword.name-da}} deployable architecture version 1.1.1 [is released](/catalog#deployable_architecture){: external}.

    - In this version, a {{site.data.keyword.secrets-manager_short}} event notification destination and topic are created in the {{site.data.keyword.en_short}} instance that is created by the deployable architecture. Email subscriptions are also configured for the new destination and topic from the list of emails that is passed in the `en_email_list` input.
    - The attachment that is created by the {{site.data.keyword.compliance_short}} member is updated to use the CIS IBM Cloud Foundations Benchmark v1.1.0 profile because version 1.0.0 is deprecated.

        You must update the profile attachment input value in the `4a - Security and Compliance Center` member configuration to `CIS IBM Cloud Foundations Benchmark v1.1.0` when you update. For more information, see [Updating to version 1.1.1](/docs/security-services?topic=security-services-known-issues#ki-update-profile) in Known issues.
        {: important}

## June 2024
{: #css-2024-06}

### 24 June 2024
{: #css-jun-2424}
{: release-note}

Introducing the {{site.data.keyword.name-da}} deployable architecture
:   The {{site.data.keyword.name-da}} deployable architecture [is released](/catalog#deployable_architecture){: external}: The deployable architecture deploys the following {{site.data.keyword.name-da}}: {{site.data.keyword.keymanagementserviceshort}}, {{site.data.keyword.secrets-manager_short}}, {{site.data.keyword.compliance_short}}, and {{site.data.keyword.sysdigsecure_full_notm}}. The deployable architecture also deploys {{site.data.keyword.en_short}} and Observability.

    For more information about using deployable architectures with projects, see the blog posts [Projects and Cost Estimation: How IBM Cloud is Revolutionizing Complex Workloads for Enterprises](https://www.ibm.com/blog/announcement/projects-and-cost-estimation/) and [Turn Your Terraform Templates into Deployable Architectures](https://www.ibm.com/blog/turn-your-terraform-templates-into-deployable-architectures/).
