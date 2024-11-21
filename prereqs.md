---

copyright:
  years: 2024
lastupdated: "2024-11-18"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Preparing to deploy the Essential Security and Observability Services deployable architecture
{: #prereqs}

The Essential Security and Observability Services deployable architecture is a preconfigured set of infrastructure as code assets that are designed to deploy select {{site.data.keyword.cloud_notm}} security services according to best practices. The included security services are crucial for helping ensure that you have a robust security and compliance strategy for your applications and data. By using this architecture, you can accelerate your deployment and tailor it to meet your organizations security and compliance requirements.
{: shortdesc}

When you deploy the architecture, you can:

* **Implement security**: The architecture provisions security services such as {{site.data.keyword.keymanagementservicelong_notm}} and {{site.data.keyword.secrets-manager_full_notm}} that can help you to manage sensitive data for your organization. 

* **Ensure observability**: The architecture provisions observability services such as {{site.data.keyword.la_full_notm}}, {{site.data.keyword.monitoringlong_notm}}, {{site.data.keyword.atracker_full_notm}}, {{site.data.keyword.en_full_notm}}, and log retention through {{site.data.keyword.cos_full_notm}} buckets.

* **Monitor for regulatory compliance**: The architecture helps to ensure regulatory compliance by provisioning {{site.data.keyword.sysdigsecure_full_notm}} to validate the configurations that are made as part of application lifecycle management against the CIS {{site.data.keyword.cloud_notm}} Foundations Benchmark profile. To see the controls that are included, go to the Essential Security and Observability Services deployable architecture catalog tile in the console and click the **Security & compliance** tab. 

## Before you deploy
{: #before-deploy-prereq}

Before you can deploy the Essential Security and Observability Services deployable architecture, you must have the following prerequisites.

* A Pay-As-You-Go or Subscription {{site.data.keyword.cloud_notm}} account. 

   Don't have one? [Create one](/docs/account?topic=account-account-getting-started). Have a Trial or Lite account? [Upgrade your account](/docs/account?topic=account-upgrading-account).
   {: tip}

* The required level of access to deploy and manage resources in the account.
* An [{{site.data.keyword.cloud_notm}} API Key]((/docs/account?topic=account-userapikey&interface=terraform#create_user_key-api-terra)) in the target account with the suffienct permissions. Be sure to save the API key value for a later configuration.

   * **Evaluation environments**: If your environment is used for evaluating, grant the Administrator role on the **IAM Identity Service**, **All Identity and Access enabled services**, **Activity Tracker Event Routing** and **All Account Management** services.
   * **Production environments**: If your environment is used for production resources, restrict access to the minimum permissions level as indicated in the **Permissions** tab of the details page of the deployable architecture catalog entry.

   For more information, see [Using an API key with Secrets Manager to authorize a project to deploy an architecture](/docs/secure-enterprise?topic=secure-enterprise-authorize-project).

* Optional: Install the {{site.data.keyword.cloud_notm}} CLI Project plug-in by running the `ibmcloud plugin install project` command. For more information, see the [Project CLI reference](/docs/cli?topic=cli-projects-cli).
* Optional: Familiarize yourself with the [Customization options](/docs/security-hub?topic=security-hub-customize-css).

You might see notifications in {{site.data.keyword.cloud_notm}} Projects that new versions of a configuration are available. You can ignore these messages because they do not prevent you from deploying the stack. No specific action is required from you. These notifications are expected, as we are rapidly iterating on the development of the underlying components. As new stack versions become available, the versions of the underlying components are also updated.
{: tip}
