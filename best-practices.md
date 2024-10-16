---

copyright:
  years: 2024
lastupdated: "2024-10-16"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# Best practices
{: #best-practices}

As you transition your workloads to {{site.data.keyword.cloud_notm}}, be sure to keep the following best practices in mind. These best practices around assigning access, managing secrets, and configuring deployments can help ensure that your compliance audits run smoothly.

## Follow the principle of least privilege
{: #bp-access}

It is always a best practices to assign each user in your account the least amount of access that is required for perform the duties of their role. For example, your organization might have a compliance focal who wants to use {{site.data.keyword.compliance_short}} to manage the collection of data for compliance audits. For that focal to be able to perform the required tasks in your account, they must have access to the {{site.data.keyword.compliance_short}}, {{site.data.keyword.en_short}}, and Cloud Object Storage services through IAM. If they are managing compliance for an entire enterprise or a specific integration, then additional permissions can be provided.

Ensuring the proper configuration of IAM policies is one of the largest factors in reducing the cost of a data breach per the [IBM Cost of Data Breach 2024 report](https://www.ibm.com/reports/data-breach){: external}.

Depending on the size of your organization, you might be required to manage very different levels of access. It is always a best practice to assign a user in your account the least amount of access required to perform the duties of their role. 
{: tip}

## Take advantage of access groups
{: #bp-groups}

Through the Identity and Access Management service, you can add the users or resources in your account to access groups based on role or required permissions. By using these groups, you can minimize the number of necessary policies that you need to assign and manage in your account. For example, if you have a team of people all working on the same project that uses the same resources, you can create a group for those users and assign permissions to the group rather than to each individual person. For help getting started, see [Creating access groups](/docs/account?topic=account-groups).

Does a user need this permission for a short time period? It might be better practice to use a trusted profile. [Learn more](/docs/secure-enterprise?topic=secure-enterprise-access-enterprises#bp-enterprise-access-include-compare-accessgroups-trustedprofiles).
{: tip}

## Tag your resources
{: #bp-tags}

The easiest way to control access to the resources and service IDs in your account at scale is by using access management tags. By assigning access to resources and service IDs that have specific tags attached to them, you can avoid repeatedly updating your defined policies. For more information, see [Controlling access by using tags](/docs/account?topic=account-access-tags-tutorial).

## Enforce MFA
{: #bp-mfa}

While multifactor authentication is typically a choice made by each organization, it is a best practice and more and more compliance regulations are beginning to require it. Be sure that you know which standards and regulations that your organization is required to be in compliance with. To configure MFA, you can create a settings template that defines the level of MFA that you want your company to follow. Then, assign the settings template to all account groups. Learn more about [Setting up Multifactor authentication](/docs/account?topic=account-enablemfa).


## Encrypt the data in your account
{: #bp-mng-secrets}

Through the use of credentials, keys, or certificates it is important that your data remain secure throughout your account. It is important to think about encryption at every level, whether it's at rest, in motion, or in use. To evaluate about which secrets management tool is best for your organization, see [Which service should I use](/docs/security-hub?topic=security-hub-manage-secrets-ibm-cloud).


## Ensure the proper rotation of secrets
{: #bp-secret-rotate}

Regardless of which service you are using or what type of secret that you are rotating, it is crucial to the security of your applications that the rotation of your secrets is completed regularly and in a secure manner. To ensure that you never miss a rotation, it is recommended tht you configure alerts. Check out the following links to learn more about the best practices of each service and secret type:

* [Rotating secrets through Secrets Manager](/docs/secrets-manager?topic=secrets-manager-best-practices-rotate-secrets)
* [Rotating keys in Key Protect](/docs/key-protect?topic=key-protect-key-rotation)
* [Rotating keys in Hyper Protect Crypto Services](/docs/hs-crypto?topic=hs-crypto-set-rotation-policy)


## Run recurring compliance checks
{: #bp-compliance}

While you can make all of the correct choices the first time that you configure your account, over time additional policies are set, users leave your company, or resources can be updated by users in your account in a way in which leaves you out of compliance. To ensure that your secure account remains a secure account, it is highly recommended that you use {{site.data.keyword.compliance_short}} or {[wp]} to continuously validate the compliance posture of your account. 

Running an evaluation does not ensure regulatory compliance. An evaluation provides a point in time statement of your current posture for a specific resource. It is your responsibility to review and interpret the results to ensure that your organization is adhering to the controls that are required for your industry. 
{: important}
