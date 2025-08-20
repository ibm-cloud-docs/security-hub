---

copyright:
  years: 2024
lastupdated: "2025-08-19"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Best practices for access, secrets, and deployment configuration
{: #best-practices}

As you transition your workloads to {{site.data.keyword.cloud_notm}}, be sure to keep the following best practices in mind. These best practices around assigning access, managing secrets, and configuring deployments can help ensure that your compliance audits run smoothly.

## Follow the principle of least privilege
{: #bp-access}

It's always a best practice to assign each user in your account the least amount of access that is required for them to perform the duties of their role. For example, your organization might have a compliance-focal who wants to use {{site.data.keyword.compliance_short}} to manage the collection of data for compliance audits. For the focal to be able to perform the required tasks in your account, they must have access to the {{site.data.keyword.compliance_short}}, {{site.data.keyword.en_short}}, and Cloud Object Storage services through IAM. If they are managing compliance for an entire enterprise or a specific integration, then more permissions can be provided.

Helping ensure the proper configuration of IAM policies is one of the greatest factors in reducing the cost of a data breach per the [IBM Cost of Data Breach 2024 report](https://www.ibm.com/reports/data-breach){: external}.


## Take advantage of access groups
{: #bp-groups}

Through the Identity and Access Management service, you can add the users or resources in your account to access groups based on role or required permissions. By using these groups, you can minimize the number of necessary policies that you need to assign and manage in your account. For example, if your team project uses the same resources, you can create a group and assign permissions to the group rather than to each individual. For help with getting started, see [Creating access groups](/docs/account?topic=account-groups).

Does a user need this permission for a short time period? It might be better practice to use a trusted profile. [Learn more](/docs/enterprise-management?topic=enterprise-management-access-enterprises#bp-enterprise-access-include-compare-accessgroups-trustedprofiles).
{: tip}

## Tag your resources
{: #bp-tags}

The best way to control access to the resources and service IDs in your account at scale is by using access management tags. By assigning access to resources and service IDs that have specific tags that are attached to them, you can avoid repeatedly updating your defined policies. For more information, see [Controlling access by using tags](/docs/account?topic=account-access-tags-tutorial).

## Enforce MFA
{: #bp-mfa}

While multifactor authentication is typically a choice made by each organization, more compliance regulations are requiring it. Be sure that you know which standards and regulations that your organization is required to be in compliance with. To configure MFA, you can create a settings template that defines the level of MFA that you want your company to follow. Then, assign the settings template to all account groups. Learn more about [Setting up Multifactor authentication](/docs/account?topic=account-enablemfa).


## Encrypt the data in your account
{: #bp-mng-secrets}

By using credentials, keys, or certificates it is important that your data remains secure throughout your account. It is important to think about encryption at every level, whether it's at rest, in motion, or in use. To evaluate about which secrets management tool is best for your organization, see [Which service should I use](/docs/security-hub?topic=security-hub-manage-secrets-ibm-cloud).


## Ensure the proper rotation of secrets
{: #bp-secret-rotate}

Regardless of which service you are using or what type of secret that you are rotating, it is crucial to the security of your applications that the rotation is completed securely and regularly. To help ensure that you never miss a rotation, it's recommended that you configure alerts. Check out the following links to learn more about the best practices of each service and secret type:

* [Rotating secrets through Secrets Manager](/docs/secrets-manager?topic=secrets-manager-best-practices-rotate-secrets)
* [Rotating keys in Key Protect](/docs/key-protect?topic=key-protect-key-rotation)
* [Rotating keys in Hyper Protect Crypto Services](/docs/hs-crypto?topic=hs-crypto-set-rotation-policy)


## Run recurring compliance checks
{: #bp-compliance}

The first time that an account is configured it is typically done carefully. But, as more policies are set, users leave your company, or resources are updated you can quickly become uncompliant. To help ensure that your organization remains secure, it is highly recommended that you use {{site.data.keyword.compliance_short}} or {{site.data.keyword.sysdigsecure_short}} to continuously validate the compliance posture of your account. 

Running an evaluation does not help ensure regulatory compliance. An evaluation provides a point in time statement of your current posture for a specific resource. It is your responsibility to review and interpret the results to help ensure that your organization is adhering to the controls that are required for your industry. 
{: important}
