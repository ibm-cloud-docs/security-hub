---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# My deployment fails when creating a resource
{: #ts-platform-metrics}
{: troubleshoot}

Your deployment fails with an error about creating a resource instance.
{: shortdesc}

You receive the following error.
{: tsSymptoms}

> [ERROR] Error when creating resource instance: Please contact the Service Provider for this error. [500, Internal Server Error] Sysdig provision request return code: 500 response: {"errors":[{"reason":"Exception","message":"Cannot update default receiver for instance 'c4ae5659-4a08-47ce-a955-968211bfcf8e' while it is enabled for 'a2f9a02e-ba89-491c-a702-52fe24881566' display name null"}]}

A platform metrics instance is already installed in the account.
{: tsCauses}

Set the `enable_platform_logs_metrics` input variable to `false`.
{: tsResolve}
