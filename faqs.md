---

copyright:
  years: 2024
lastupdated: "2025-09-01"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# FAQ for Cloud foundation for security and observability deployable architecture
{: #faqs}

FAQ for the Cloud foundation for security and observability deployable architecture. To find all FAQs for {{site.data.keyword.cloud}}, see our [FAQ library](/docs/faqs).
{: shortdesc}

## What is a deployable architecture?
{: #what-is-da}
{: faq}

A deployable architecture is a combination of capabilities from one or more technologies that solve a customer-defined problem, and it can have one or more reference architectures based on the customer business needs. For more information about deployable architectures, see [What are modules and deployable architectures?](/docs/secure-enterprise?topic=secure-enterprise-understand-module-da) and read about infrastructure architectures in [Running secure enterprise workloads on IBM Cloud](/docs/overview?topic=overview-secure-enterprise#define-architecture).

If you prefer to manage your own Terraform state and pipelines, you can also build the same security foundation using individual [Terraform IBM Modules](https://github.com/terraform-ibm-modules){: external} rather than deploying the full deployable architecture through {{site.data.keyword.cloud_notm}} Projects.

## What is infrastructure as code?
{: #what-is-iac}
{: faq}

Infrastructure as code (IaC) is code to manage and provision infrastructure (for example, networks, virtual machines, load-balancers, clusters, services, and connection topology) in a descriptive model rather than by using manual processes.

With IaC, code defines your infrastructure, specifying your resources and their configuration. Your infrastructure code is treated the same as app code so that you can apply DevOps core practices such as version control, testing, and continuous monitoring. The Cloud foundation for security and observability deployable architecture use [Terraform](https://developer.hashicorp.com/terraform){: external} to specify the infrastructure and [{{site.data.keyword.bplong_notm}}](/docs/schematics?topic=schematics-getting-started) to manage the deployment.

{{site.data.keyword.cloud_notm}} also provides a library of open-source [Terraform IBM Modules](https://github.com/terraform-ibm-modules){: external} — reusable, production-ready Terraform configurations for individual {{site.data.keyword.cloud_notm}} services. Teams that manage their own Terraform pipelines can use these modules to provision the same security services that underpin the deployable architecture, with full control over state, configuration, and deployment workflow.

## Can I use Terraform IBM Modules to deploy or extend this architecture?
{: #what-is-tim}
{: faq}

Yes. The Cloud foundation for security and observability deployable architecture is built on [Terraform IBM Modules (TIM)](https://github.com/terraform-ibm-modules){: external} — a library of open-source, {{site.data.keyword.IBM_notm}}-maintained Terraform modules. If you want to deploy individual components of the architecture independently, or extend the architecture with additional services, you can reference these modules directly in your own Terraform configurations.

The following modules are used as part of this architecture:

- [`terraform-ibm-key-protect`](https://github.com/terraform-ibm-modules/terraform-ibm-key-protect){: external} — Provisions {{site.data.keyword.keymanagementserviceshort}}
- [`terraform-ibm-kms-all-inclusive`](https://github.com/terraform-ibm-modules/terraform-ibm-kms-all-inclusive){: external} — Provisions Key Protect with keys and key rings
- [`terraform-ibm-secrets-manager`](https://github.com/terraform-ibm-modules/terraform-ibm-secrets-manager){: external} — Provisions {{site.data.keyword.secrets-manager_short}}
- [`terraform-ibm-scc-workload-protection`](https://github.com/terraform-ibm-modules/terraform-ibm-scc-workload-protection){: external} — Provisions SCC Workload Protection
- [`terraform-ibm-iam-access-group`](https://github.com/terraform-ibm-modules/terraform-ibm-iam-access-group){: external} — Manages IAM access groups
- [`terraform-ibm-iam-account-settings`](https://github.com/terraform-ibm-modules/terraform-ibm-iam-account-settings){: external} — Manages account-level security settings
- [`terraform-ibm-cbr`](https://github.com/terraform-ibm-modules/terraform-ibm-cbr){: external} — Manages Context-Based Restrictions
- [`terraform-ibm-hpcs`](https://github.com/terraform-ibm-modules/terraform-ibm-hpcs){: external} — Provisions Hyper Protect Crypto Services

## How do I estimate costs?
{: #what-is-project-cost}
{: faq}

You can view and estimate of starting costs for a variation of the deployable architecture from the {{site.data.keyword.cloud_notm}} catalog details page. When you deploy by using {{site.data.keyword.cloud}} projects, the starting costs for the project are estimated from the validation window after your changes to the configuration are saved and validated.

## How do I keep up with changes to my deployable architecture?
{: #what-is-notifications}
{: faq}

To make sure you stay up to date with the items that need attention in your deployable architecture, enable event notifications for projects. For more information, see [Enabling event notifications for projects](/docs/secure-enterprise?topic=secure-enterprise-event-notifications-events).
