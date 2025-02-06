---

copyright:
  years: 2024
lastupdated: "2025-02-06"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for the Essential Security and Observability Services deployable architecture
{: #release-notes}

Use these release notes to learn about the latest updates to the Essential Security and Observability Services deployable architecture. The entries are grouped by date.
{: shortdesc}

## November 2024
{: #security-services-date-for-update-2024-11}
{: release-note}

### 18 November 2024
{: #security-services-date-for-update-nov-1824}
{: release-note}

Version 2.1.0 of the Essential Security and Observability Services deployable architecture deployable architecture is available
:   The Essential Security and Observability Services deployable architecture deployable architecture version 2.1.0 [is released](/catalog#deployable_architecture){: external}.

    If you are upgrading from an older version, ensure that you only proceed to upgrade from version 1.5.0 or later. If you attempt to upgrade from an older version, the Observability member will fail as you cannot disable Log Analysis log archiving and delete an IBM Log Analysis instance as part of the same deployment. {: note}

    - When you upgrade, all deployable architecture stack members are updated to their latest versions.
    - A fix was added to the {{site.data.keyword.compliance_short}} deployable architecture to fix a backend change which was causing the below error to occur when configuring integration with {{site.data.keyword.en_short}}:  
        `Error setting event_notifications: Invalid address to set: []string{"event_notifications", "0", "source_description"}`
    - All of the deployable architecture stack members (with the exception of the Observability member due to this [provider bug](https://github.com/IBM-Cloud/terraform-provider-ibm/issues/5824)), will now use the IBM Cloud regional private endpoint or global private endpoint by default. The regional private endpoint is given higher precedence. In order to use the private endpoint from an IBM Cloud resource, one must have a [VRF-enabled](https://cloud.ibm.com/docs/account?topic=account-vrf-service-endpoint&interface=ui) account. This can be overriden and set back to public by editing each of the deployable architecture stack members and changing the value of the `provider_visibility` input.

### 4 November 2024
{: #security-services-date-for-update-nov-0424}
{: release-note}

Version 2.0.0 of the Essential Security and Observability Services deployable architecture deployable architecture is available
:   The Essential Security and Observability Services deployable architecture deployable architecture version 2.0.0 [is released](/catalog#deployable_architecture){: external}.

    If you are upgrading from an older version, ensure that you only proceed to upgrade from version 1.5.0. If you attempt to upgrade from an older version, the Observability member will fail as you cannot disable Log Analysis log archiving and delete an IBM Log Analysis instance as part of the same deployment. {: note}

    - IBM Log Analysis is now fully removed from the solution. Upgrading to this version will destroy the IBM Log Analysis instance that was provisioned with older versions. IBM Cloud Logs should now be used for managing logs. Support for Cloud Logs was added in version 1.5.0.
    - IBM Cloud Logs is now configured with Event Notifications by default.
    - The scope of the service authorization policies that are created in the Observability, Event Notifications, and Security and Compliance Center members to allow the Object storage service to read the encryption key from the Key Protect service have all been updated to only grant access to read the exact encryption key that is being used. Previouslly the scope was allowing reader access to the whole Key Protect instance. If upgrading from an older version, you will see the old authorization policies being deleted, and new ones being created. The new one is created before the old one is deleted to prevent any disruption to every day services.
    - The Event Notifications member has been updated to communcate with the Object storage bucket over the direct endpoint. Previously it was using the public endpoint. This result in a non disruptive update in place if upgrading from an older version.
    - The Object storage bucket created by the Event Notifications member has been updated so the Monitoring instance is no longer explicitly passed to it. The bucket metrics will still be monitored, however metrics will be sent to the instance associated to the container's location unless otherwise specified in the Metrics Router service configuration. This result in a non disruptive update in place if upgrading from an older version.
    - An update in place will be done on all KMS key ring created by the member DAs as the `force_delete` option has been deprecated by the service. This has no impact to any services as the value is not being used by the backend.

## October 2024
{: #security-services-date-for-update-2024-10}

### 11 October 2024
{: #security-services-date-for-update-oct-1124}
{: release-note}

Version 1.5.0 of the Essential Security and Observability Services deployable architecture deployable architecture is available
:   The Essential Security and Observability Services deployable architecture deployable architecture version 1.5.0 [is released](/catalog#deployable_architecture){: external}.

    - When you upgrade, all deployable architecture stack members are updated to their latest versions.
    - The Observability deployable architecture will now deploy both IBM Cloud Logs and IBM Cloud Log Analysis. As IBM Cloud Log Analysis is now a deprecated service, which is replaced by IBM Cloud Logs, Log Analysis log archiving is now disabled which is required before the Log Analysis instance can be deleted.
    - An Activity Tracker target is also now created for the IBM Cloud Logs instance, and an additional route is also set up to send activity tracker events to it. It means that activity tracker events are being sent to both an Object Storage bucket for long term storage, and to IBM Cloud Logs so they can be easily viewed.

    In this version, the instance of IBM Cloud Logs will not have Event Notifications integration enabled, however this support will be coming in version 2.0.0. {: note}

    - Since Log Analysis log archiving is now disabled, it means if you are upgrading from a previous version, the Object Storage bucket that was created by the Observability deployable architecture will be destroyed. If do not wan't to destroy this bucket and wan't to keep managing it through the Observability member deployable architecture, follow these steps:

        1.  In the {{site.data.keyword.cloud_notm}} console, click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Projects**.
        1.  Click the project with the stacked deployable architecture that you want to update.
        1.  Click the **Configurations** tab.
        1.  Update the version to 1.5.0 but do not proceed to validate or deploy yet.
        1.  In the row for the member configuration named `2 - Observability`, click the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") and select **Edit**.
        1.  Click the **Optional** tab in the **Configure** section.
        1.  Find the **manage_log_archive_cos_bucket** input variable and change the value to `true`.
        1.  Click **Save**.
        1.  Follow the steps in [Step 3. Validate and deploy the architecture](/docs/security-hub?topic=security-hub-deploy-css#deploy-validate) to validate and deploy all deployable architectures in the stack.

    - In version 2.0.0, Log Analysis will be full removed, however if you wan't to delete your Log Analysis instance before then, you can follow the below steps, but only after version 1.5.0 has been fully deployed:

        1.  In the {{site.data.keyword.cloud_notm}} console, click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Projects**.
        1.  Click the project with the stacked deployable architecture that you want to update.
        1.  Click the **Configurations** tab.
        1.  In the row for the member configuration named `2 - Observability`, click the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") and select **Edit**.
        1.  Click the **Optional** tab in the **Configure** section.
        1.  Find the **log_analysis_provision** input variable and change the value to `false`.
        1.  Click **Save**.
        1.  Follow the steps in [Step 3. Validate and deploy the architecture](/docs/security-services?topic=security-services-deploy-css#deploy-validate) to validate and deploy the deployable architecture.

## September 2024
{: #css-2024-09}

### 6 September 2024
{: #css-sep-0624}
{: release-note}

Version 1.4.1 of the Essential Security and Observability Services deployable architecture is available
:   The Essential Security and Observability Services deployable architecture version 1.4.1 [is released](/catalog#deployable_architecture){: external}.

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

Version 1.3.1 of the Essential Security and Observability Services deployable architecture is available
:   The Essential Security and Observability Services deployable architecture version 1.3.1 [is released](/catalog#deployable_architecture){: external}.

    - Updates the {{site.data.keyword.secrets-manager_short}} member deployable architecture to version 1.17.1, which supports the use of `existing_secrets_manager_crn`.
    - Adds a `secret_manager_iam_engine_enabled` input variable to configure credentials for the {{site.data.keyword.secrets-manager_short}} IAM credentials engine. The default value is `false`.

## July 2024
{: #css-2024-07}

### 29 July 2024
{: #css-jul-2924}
{: release-note}

Version 1.2.1 of the Essential Security and Observability Services deployable architecture is available
:   The Essential Security and Observability Services deployable architecture version 1.2.1 [is released](/catalog#deployable_architecture){: external}.

     - When you upgrade, all deployable architecture members are updated to their latest versions.
     - A new `existing_kms_instance_crn` input variable adds support to use an existing key management service instance. By default, a new {{site.data.keyword.keymanagementserviceshort}} instance is created.
     - Fixes an issue in which activity tracking was not enabled for {{site.data.keyword.cos_full_notm}} buckets. By default, {{site.data.keyword.cos_short}} buckets that are created by the deployable architecture now have activity tracking enabled. When you upgrade, existing buckets are updated when you upgrade to this version.
     - Fixes an issue in which the {{site.data.keyword.en_short}} member created {{site.data.keyword.cos_short}} destinations instead of {{site.data.keyword.cos_short}} integrations that are needed to store failed events. When you upgrade, these destinations are destroyed.

### 1 July 2024
{: #css-jul-0124}
{: release-note}

Version 1.1.1 of the Essential Security and Observability Services deployable architecture is available
:   The Essential Security and Observability Services deployable architecture version 1.1.1 [is released](/catalog#deployable_architecture){: external}.

    - In this version, a {{site.data.keyword.secrets-manager_short}} event notification destination and topic are created in the {{site.data.keyword.en_short}} instance that is created by the deployable architecture. Email subscriptions are also configured for the new destination and topic from the list of emails that is passed in the `en_email_list` input.
    - The attachment that is created by the {{site.data.keyword.compliance_short}} member is updated to use the CIS IBM Cloud Foundations Benchmark v1.1.0 profile because version 1.0.0 is deprecated.

        You must update the profile attachment input value in the `4a - Security and Compliance Center` member configuration to `CIS IBM Cloud Foundations Benchmark v1.1.0` when you update.
        {: important}

## June 2024
{: #css-2024-06}

### 24 June 2024
{: #css-jun-2424}
{: release-note}

Introducing the Essential Security and Observability Services deployable architecture
:   The Essential Security and Observability Services deployable architecture [is released](/catalog#deployable_architecture){: external}: The deployable architecture deploys the following: {{site.data.keyword.keymanagementserviceshort}}, {{site.data.keyword.secrets-manager_short}}, {{site.data.keyword.compliance_short}}, and {{site.data.keyword.sysdigsecure_full_notm}}. The deployable architecture also deploys {{site.data.keyword.en_short}} and Observability.

    For more information about using deployable architectures with projects, see the blog posts [Projects and Cost Estimation: How IBM Cloud is Revolutionizing Complex Workloads for Enterprises](https://www.ibm.com/new/announcements/projects-and-cost-estimation) and [Turn Your Terraform Templates into Deployable Architectures](https://www.ibm.com/think/insights/turn-your-terraform-templates-into-deployable-architectures).
