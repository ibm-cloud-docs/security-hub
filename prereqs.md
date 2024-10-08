---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords:

subcollection: security-services

---

{{site.data.keyword.attribute-definition-list}}

# Planning for the {{site.data.keyword.name-da}} deployable architecture
{: #prereqs}

Before you begin the deployment of a {{site.data.keyword.name-da}} deployable architecture, make sure that you understand and meet the prerequisites.

## Confirm your {{site.data.keyword.cloud_notm}} settings
{: #css-cloud-prereqs}

Complete the following steps before you deploy the {{site.data.keyword.name-da}} deployable architecture.

1.  Confirm or set up an {{site.data.keyword.cloud_notm}} account:

    Make sure that you have an {{site.data.keyword.cloud_notm}} Pay-As-You-Go or Subscription account:

    - If you don't have an {{site.data.keyword.cloud_notm}} account, [create one](/docs/account?topic=account-account-getting-started).
    - If you have a Trial or Lite account, [upgrade your account](/docs/account?topic=account-upgrading-account).
1.  Configure your {{site.data.keyword.cloud_notm}} account:
    1.  Log in to [{{site.data.keyword.cloud_notm}}](https://cloud.ibm.com) with the {{site.data.keyword.ibmid}} you used to set up the account. This {{site.data.keyword.ibmid}} user is the account owner and has full IAM access.
    1.  [Complete the company profile](/docs/account?topic=account-contact-info) and contact information for the account. This profile is required to stay in compliance with {{site.data.keyword.cloud_notm}} Financial Services profile.

## Set the IAM permissions
{: #css-iam-prereqs}

1.  Set up account access ({{site.data.keyword.iamshort}} (IAM)):

    1.  Create an {{site.data.keyword.cloud_notm}} [API key](/docs/account?topic=account-userapikey&interface=terraform#create_user_key-api-terra) in the target account with sufficient permissions. This API key authorizes the project to deploy to a target account and is required to deploy your architecture. For more information, see [Using an API key with Secrets Manager to authorize a project to deploy an architecture](/docs/secure-enterprise?topic=secure-enterprise-authorize-project).
    1.  Store the value of the API key because you need it later.

- On evaluation environments, grant the Administrator role on the **IAM Identity Service**, **All Identity and Access enabled services**, and on the **Activity Tracker Event Routing** and **All Account Management** services.
- For a production environment, restrict access to the minimum permissions level as indicated in the **Permissions** tab of the deployable architecture details page.

## Optional planning information
{: #css-optional-plan}

The following items are not required for {{site.data.keyword.name-da}} deployable architecture, but might support your deployment.

- Install the {{site.data.keyword.cloud_notm}} CLI Project plug-in by running the `ibmcloud plugin install project` command. For more information, see the [Project CLI reference](/docs/cli?topic=cli-projects-cli).
- Familiarize yourself with the [Customization options](/docs/security-services?topic=security-services-customize-css).

You might see notifications in {{site.data.keyword.cloud_notm}} Projects that new versions of a configuration are available. You can ignore these messages because they do not prevent you from deploying the stack. No specific action is required from you. These notifications are expected, as we are rapidly iterating on the development of the underlying components. As new stack versions become available, the versions of the underlying components will also be updated.
{: tip}
