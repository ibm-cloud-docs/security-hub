---

copyright:
  years: 2024, 2025
lastupdated: "2025-06-10"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for the Essential Security and Observability Services deployable architecture
{: #release-notes}

Use these release notes to learn about the latest updates to the Essential Security and Observability Services deployable architecture. The entries are grouped by date.
{: shortdesc}

## June 2025
{: #security-services-date-for-update-2025-10}
{: release-note}

### 10 June 2025
{: #security-services-date-for-update-jun-1025}
{: release-note}

Version 3.0.0 of the Essential Security and Observability Services deployable architecture deployable architecture is available
:   The Essential Security and Observability Services deployable architecture deployable architecture version 3.0.0 [is released](/catalog#deployable_architecture){: external}.

   - Migration to Security and Compliance Center Workload Protection for Cloud Security Posture Management
      - This solution will no longer provision an instance of the Security and Compliance Center service as it has been deprecated and new instances cannot be provisioned after 16th June 2025.
      - The solution will now provision a new instance of [App Configuration](app-configuration) and [Security and Compliance Center Worklaod Protection](workload-protection) with [Cloud Security Posture Management (CSPM)](workload-protection?topic=workload-protection-about) enabled by default.
      - If you are upgrading from a previous version of the solution, you will continue to see the member named `4a - Security and Compliance Center` so that you can decide when you want to delete the Security and Compliance Center instance and associated Object Storage bucket. Please be aware that this config also has an instance of Security and Compliance Center Worklaod Protection deployed as part of it, however it is not enabled with Cloud Security Posture Management (CSPM) and is safe to delete as the new instance that is now created by the solution will be used going forward.
      - For more information, see [Security and Compliance Center transition](security-compliance?topic=security-compliance-scc-transition).
   - The service to service authorization that is used to allow the ATracker service write to Object Storage has been updated so that the scope of the policy is scoped to the exact Object Storage bucket.
      - If upgrading from an older version, you will see the old authorization policy being deleted, a new ones being created. The new one is created before the old one is deleted to prevent any disruption to every day services.

## April 2025
{: #security-services-date-for-update-2025-04}
{: release-note}

### 3 April 2025
{: #security-services-date-for-update-apr-0425}
{: release-note}

Version 2.2.0 of the Essential Security and Observability Services deployable architecture deployable architecture is available
:   The Essential Security and Observability Services deployable architecture deployable architecture version 2.2.0 [is released](/catalog#deployable_architecture){: external}.

   - When you upgrade, all deployable architecture stack members are updated to their latest versions.
   - Updates to the way the Secrets Manager IAM credentials engine is managed:
      - The input `secret_manager_iam_engine_enabled` has changed. The UI now shows the option: `Disable Secrets Manager IAM credentials engine auth policy creation?`. The default value of this is `false` so that the Secrets Manager IAM credentials engine is enabled by default.
      - The enablement of the engine is now handled by service to service authorisation policies:
         - grants the Secrets Manager instance 'Operator' access to the IAM identity service
         - grants the Secrets Manager instance 'Groups Service Member Manage' access to the IAM groups service
      - If upgrading from a previous release where you had set `secret_manager_iam_engine_enabled` to `true`, you will now see the expected deletion of the service ID and related apikey as these are no longer needed due to the new service to service authorisation policies.
   - The scope of the service authorization policy that is created in the Secrets Manager member to allow the instance to read the encryption key from the Key Protect service has been updated to only grant access to read the exact encryption key that is being used. Previously the scope was allowing reader access to the whole Key Protect instance. If upgrading from an older version, you will see the old authorization policy being deleted, a new ones being created. The new one is created before the old one is deleted to prevent any disruption to every day services.
   - The {{site.data.keyword.compliance_short}} deployable architecture now creates a service authorization policy that grants the {{site.data.keyword.compliance_short}} instance `Event Source Manager` access to the {{site.data.keyword.en_short}} instance.
   - Observability updates:
      - The `enable_platform_logs_metrics` input has been split into 2 separate inputs:
         - `enable_platform_metrics`: To enable platform metrics on the Cloud Monitoring instance that is provisioned
         - `logs_routing_tenant_regions`: To define a list of regions you want platform logs routed from into the Cloud Logs instance
      - Metrics routing is now enabled by default:
         - A new target is set up that points to the Cloud Monitoring instance that is provisioned
         - A new route is set up to route metrics to the new target
         - The primary metrics region will be set to the same region that the Cloud Monitoring instance was provisioned to
         - The default receiver will be set to the Cloud Monitoring instance that is provisioned
      - The service authorisation policy between Cloud Logs and Event Notifications has been updated to allow the `Viewer` role. Previously it only had the `Event Source Manager` role. 

## November 2024
{: #security-services-date-for-update-2024-11}
{: release-note}

### 18 November 2024
{: #security-services-date-for-update-nov-1824}
{: release-note}

Essential Security and Observability Services deployable architecture deployable architecture version 2.1.0
:   The Essential Security and Observability Services deployable architecture deployable architecture version 2.1.0 [is now available](/catalog#deployable_architecture){: external} with the following changes.

   Due to the deprecation and subsequent replacement of functionality in the Observability architecture, you must be currently using version 1.5.0 or higher to upgrade to this version.
   {: note}


   - When you upgrade, all deployable architecture stack members are updated to their latest versions.
   - A fix was added to the {{site.data.keyword.compliance_short}} deployable architecture to fix a backend change which was causing the below error to occur when configuring integration with {{site.data.keyword.en_short}}:  
        `Error setting event_notifications: Invalid address to set: []string{"event_notifications", "0", "source_description"}`
   - All of the deployable architecture stack members (with the exception of the Observability member due to this [provider bug](https://github.com/IBM-Cloud/terraform-provider-ibm/issues/5824)), will now use the IBM Cloud regional private endpoint or global private endpoint by default. The regional private endpoint is given higher precedence. In order to use the private endpoint from an IBM Cloud resource, one must have a [VRF-enabled](https://cloud.ibm.com/docs/account?topic=account-vrf-service-endpoint&interface=ui) account. This can be overriden and set back to public by editing each of the deployable architecture stack members and changing the value of the `provider_visibility` input.

### 4 November 2024
{: #security-services-date-for-update-nov-0424}
{: release-note}

Essential Security and Observability Services deployable architecture deployable architecture version 2.0.0
:   The Essential Security and Observability Services deployable architecture deployable architecture version 2.0.0 [is now available](/catalog#deployable_architecture){: external} with the following changes.

   Due to the deprecation and subsequent replacement of functionality in the Observability architecture, you must be currently using version 1.5.0 to upgrade to this version.
    {: note}

   * {{site.data.keyword.cloud_notm}} Logs is now used to manage logging within the solution and is configured in the {{site.data.keyword.en_short}} architecture by default.
   * The authorization policies that are created as part of the Observability, {{site.data.keyword.en_short}}, and {{site.data.keyword.compliance_short}} deployments are updated to allow the Cloud Object Storage service to read only the encryption key provided that is used by the {[kp]} service. Previously, the policy allowed read access for the entirety of the {[kp]} service. When the architecture is updated from a previous version, the old authorization policy is automatically deleted after the new one is created to ensure that there are no disruptions to every day workflows. 
   * The Cloud Object Storage bucket that is created during the {{site.data.keyword.en_short}} deployment is updated to prevent the Monitoring instance from being explicitly passed to it. The bucket metrics are still monitored, but they are forwarded to the instance that is associated with the container's location unless otherwise specified in the Metrics Router service configuration. 
   * An update in place is done on the key management service key ring that is created by the included architectures as the `force_delete` option is deprecated by the service. There is no impact to any of the included services.


## October 2024
{: #security-services-date-for-update-2024-10}

### 11 October 2024
{: #security-services-date-for-update-oct-1124}
{: release-note}

Version 1.5.0 of the Essential Security and Observability Services deployable architecture deployable architecture
:   The Essential Security and Observability Services deployable architecture deployable architecture version 1.5.0 [is now available](/catalog#deployable_architecture){: external} with the following changes.

   - All deployable architectures are updated to use the latest version.
   - The {{site.data.keyword.en_short}} integration is not enabled for this version.
   - The Observability architecture now deploys IBM Cloud Logs and an activity tracking target is configured. An additional route is set up for events to be sent to both a Cloud Object Storage bucket for long term storage and to the Cloud Logs service so that they can be easily viewed.
   - Due to the deprecation and subsequent replacement of technology in the Observability architecture, log archiving is now disabled. The Cloud Object Storage bucket that was created by previous versions of this architecture will be destroyed by default. If you'd like to keep the bucket and want to keep managing it through the Observability architecture, you can use the following steps to prevent deletion.

      1.  In the {{site.data.keyword.cloud_notm}} console, click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Projects**.
      1.  Click the project with the stacked deployable architecture that you want to update.
      1.  Click the **Configurations** tab.
      1.  Update the version to 1.5.0 but do not proceed to validate or deploy yet.
      1.  In the row for the member configuration named `2 - Observability`, click the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") and select **Edit**.
      1.  Click the **Optional** tab in the **Configure** section.
      1.  Find the **manage_log_archive_cos_bucket** input variable and change the value to `true`.
      1.  Click **Save**.
      1.  Follow the steps in [Step 3. Validate and deploy the architecture](/docs/security-hub?topic=security-hub-deploy-css#deploy-validate) to validate and deploy all deployable architectures in the stack.


## September 2024
{: #css-2024-09}

### 6 September 2024
{: #css-sep-0624}
{: release-note}

Version 1.4.1 of the Essential Security and Observability Services deployable architecture
:   The Essential Security and Observability Services deployable architecture version 1.4.1 [is now available](/catalog#deployable_architecture){: external} with the following changes.

   - When you upgrade, all deployable architecture members are updated to their latest versions.
   - Adds the `existing_en_instance_crn` input variable to specify an existing {{site.data.keyword.en_short}} instance.
   - Fixes an issue deploying the `4a - Security and Compliance Center` member with the profile attachment.

      If you received the `CreateAttachmentWithContext failed` error in version 1.3.1 and you removed the attachment as a workaround, follow these steps to add back the profile attachment:

      1. Upgrade to version 1.4.1 or later.
      1. In the {{site.data.keyword.cloud_notm}} console, click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Projects**.
      1. Click the project with the stacked deployable architecture that you want to update.
      1. Click the **Configurations** tab.
      1. In the row for the member configuration named `4a - Security and Compliance Center`, click the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") and select **Edit**.
      1. Click the **Optional** tab in the **Configure** section.
      1. Find the **profile_attachments** input variable and click the **Edit** icon ![Edit icon](../icons/edit-tagging.svg "Edit").
      1. Replace the empty list in the array with the following profile name:

		   ```json
			[
				"IBM Cloud Framework for Financial Services"
			]
         ```
         {: screen}

      1. Click **Save**.
      1. Follow the steps in [Step 3. Validate and deploy the architecture](/docs/security-hub?topic=security-hub-deploy-css#deploy-validate) to validate and deploy the updated deployable architecture.

## August 2024
{: #css-2024-08}

### 2 August 2024
{: #css-aug-0124}
{: release-note}

Version 1.3.1 of the Essential Security and Observability Services deployable architecture
:   The Essential Security and Observability Services deployable architecture version 1.3.1 [is now available](/catalog#deployable_architecture){: external} with the following changes.

	* To support the use of `existing_secrets_manager_crn`, the Essential Security and Observability Services deployable architecture is now updated to use version 1.17.1 of the {[sm]} architecture.
	* The input variable `secret_manager_iam_engine_enabled` is added to configure credentials for the {[sm]} IAM credentials engine. The default value is `false`.



## July 2024
{: #css-2024-07}

### 29 July 2024
{: #css-jul-2924}
{: release-note}

Version 1.2.1 of the Essential Security and Observability Services deployable architecture
:   The Essential Security and Observability Services deployable architecture version 1.2.1 [is now available](/catalog#deployable_architecture){: external} with the following changes.

	- When you upgrade, all deployable architecture members are updated to their latest versions.
	- A new `existing_kms_instance_crn` input variable adds support to use an existing key management service instance. By default, a new {{site.data.keyword.keymanagementserviceshort}} instance is created.
	- Fixes an issue in which activity tracking was not enabled for {{site.data.keyword.cos_full_notm}} buckets. By default, {{site.data.keyword.cos_short}} buckets that are created by the deployable architecture now have activity tracking enabled. When you upgrade, existing buckets are updated when you upgrade to this version.
	- Fixes an issue in which the {{site.data.keyword.en_short}} member created {{site.data.keyword.cos_short}} destinations instead of {{site.data.keyword.cos_short}} integrations that are needed to store failed events. When you upgrade, these destinations are destroyed.

### 1 July 2024
{: #css-jul-0124}
{: release-note}

Version 1.1.1 of the Essential Security and Observability Services deployable architecture
:   The Essential Security and Observability Services deployable architecture version 1.1.1 [is now avaialble](/catalog#deployable_architecture){: external} with the following updates.

	* A destination and topic are created in the {{site.data.keyword.en_short}} instance that is deployed for {[sm]}.  Email subscriptions are also configured for the new destination and topic from the list of emails that is passed in the `en_email_list` input.
	* The attachment that is created by the {{site.data.keyword.compliance_short}} deployment is updated to use the CIS {{site.data.keyword.cloud_notm}} Foundations v1.1.0 profile as the previous version is deprecated.

      You must update the profile attachment input value in the `4a - Security and Compliance Center` member configuration to `CIS IBM Cloud Foundations Benchmark v1.1.0` when you update.
      {: important}

## June 2024
{: #css-2024-06}

### 24 June 2024
{: #css-jun-2424}
{: release-note}

Introducing the Essential Security and Observability Services deployable architecture
:   The Essential Security and Observability Services deployable architecture [is released](/catalog#deployable_architecture){: external}. The deployable architecture deploys the following: {{site.data.keyword.keymanagementserviceshort}}, {{site.data.keyword.secrets-manager_short}}, {{site.data.keyword.compliance_short}}, and {{site.data.keyword.sysdigsecure_full_notm}}. The deployable architecture also deploys {{site.data.keyword.en_short}} and Observability.

	For more information about using deployable architectures with projects, see the blog posts [Projects and Cost Estimation: How IBM Cloud is Revolutionizing Complex Workloads for Enterprises](https://www.ibm.com/new/announcements/projects-and-cost-estimation){: external} and [Turn Your Terraform Templates into Deployable Architectures](https://www.ibm.com/think/insights/turn-your-terraform-templates-into-deployable-architectures){: external}.
