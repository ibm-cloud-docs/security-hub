---

copyright:
  years: 2024
lastupdated: "2024-10-13"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Preparing to deploy the {[sec-da]}
{: #prereqs}

Before you begin the deployment of a {[sec-da]}, be sure that you understand and meet the prerequisites.

## Confirm your {[cloud]} settings
{: #css-cloud-prereqs}

To work with the deployable architecture, you must have a Pay-As-You-Go or subscription {[cloud]} account.

   Don't have one? [Create one](/docs/account?topic=account-account-getting-started). Have a Trial or Lite account? [Upgrade your account](/docs/account?topic=account-upgrading-account).


## Set the IAM permissions
{: #css-iam-prereqs}

1.  Set up account access ({{site.data.keyword.iamshort}} (IAM)):

    1.  Create an {[cloud]} [API key](/docs/account?topic=account-userapikey&interface=terraform#create_user_key-api-terra) in the target account with sufficient permissions. This API key authorizes the project to deploy to a target account and is required to deploy your architecture. For more information, see [Using an API key with Secrets Manager to authorize a project to deploy an architecture](/docs/secure-enterprise?topic=secure-enterprise-authorize-project).
    1.  Store the value of the API key because you need it later.

- On evaluation environments, grant the Administrator role on the **IAM Identity Service**, **All Identity and Access enabled services**, and on the **Activity Tracker Event Routing** and **All Account Management** services.
- For a production environment, restrict access to the minimum permissions level as indicated in the **Permissions** tab of the deployable architecture details page.

## Optional planning information
{: #css-optional-plan}

The following items are not required for {[sec-da]}, but might support your deployment.

- Install the {[cloud]} CLI Project plug-in by running the `ibmcloud plugin install project` command. For more information, see the [Project CLI reference](/docs/cli?topic=cli-projects-cli).
- Familiarize yourself with the [Customization options](/docs/security-services?topic=security-services-customize-css).

You might see notifications in {[cloud]} Projects that new versions of a configuration are available. You can ignore these messages because they do not prevent you from deploying the stack. No specific action is required from you. These notifications are expected, as we are rapidly iterating on the development of the underlying components. As new stack versions become available, the versions of the underlying components will also be updated.
{: tip}
