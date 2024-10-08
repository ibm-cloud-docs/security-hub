---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords:

subcollection: security-services

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why does my {{site.data.keyword.secrets-manager_full_notm}} deployment fail with {{site.data.keyword.name-da}}?
{: #ts-secrets-mgr-trial}
{: troubleshoot}

Your deployment of {{site.data.keyword.secrets-manager_short}} failed.
{: shortdesc}

You attempted to deploy the {{site.data.keyword.secrets-manager_short}} member of the {{site.data.keyword.name-da}} deployable architecture, but it failed.
{: tsSymptoms}

An error displays in the {{site.data.keyword.secrets-manager_short}} deployment step if a Trial instance is already deployed in the same account.

And if a Trial plan instance of {{site.data.keyword.secrets-manager_short}} is undeployed and then redeployed with the Trial plan in the same account, the deployment of the {{site.data.keyword.secrets-manager_short}} member fails.

You can create only one Trial instance of {{site.data.keyword.secrets-manager_short}} in an account.
{: tsCauses}

You can deploy a Standard plan instance from the **Optional settings** of the deployable architecture.

Delete the trial instance. After deletion, also delete the service from the reclamation state.
{: tsResolve}

In {{site.data.keyword.cloud_notm}}, when you delete a resource, it doesn't immediately disappear. Instead, it enters a reclamation state, where it remains for a short time (usually 7 days) before being permanently deleted. During the reclamation state, you can recover the resource, if needed.

Run the following {{site.data.keyword.cloud_notm}} CLI commands to delete the service from the reclamation state.

The first command lists all the resources in the reclamation state.

```sh
ibmcloud resource reclamations
```
{: pre}

Find the reclamation ID of the Secrets Manager service. Use that ID in the following command.

```sh
ibmcloud resource reclamation-delete <reclamation-id>
```
{: pre}
