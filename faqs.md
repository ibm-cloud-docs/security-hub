---

copyright:
  years: 2024
lastupdated: "2025-05-02"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}

# FAQ for Essential Security and Observability Services deployable architecture
{: #faqs}

FAQ for the Essential Security and Observability Services deployable architecture. To find all FAQs for {{site.data.keyword.cloud}}, see our [FAQ library](/docs/faqs).
{: shortdesc}

## What is a deployable architecture?
{: #what-is-da}
{: faq}

A deployable architecture is a combination of capabilities from one or more technologies that solve a customer-defined problem, and it can have one or more reference architectures based on the customer business needs. For more information about deployable architectures, see [What are modules and deployable architectures?](/docs/secure-enterprise?topic=secure-enterprise-understand-module-da) and read about infrastructure architectures in [Running secure enterprise workloads on IBM Cloud](/docs/overview?topic=overview-secure-enterprise#define-architecture).

## What is infrastructure as code?
{: #what-is-iac}
{: faq}

Infrastructure as code (IaC) is code to manage and provision infrastructure (for example, networks, virtual machines, load-balancers, clusters, services, and connection topology) in a descriptive model rather than by using manual processes.

With IaC, code defines your infrastructure, specifying your resources and their configuration. Your infrastructure code is treated the same as app code so that you can apply DevOps core practices such as version control, testing, and continuous monitoring. The Essential Security and Observability Services deployable architecture use [Terraform](https://developer.hashicorp.com/terraform){: external} to specify the infrastructure and [{{site.data.keyword.bplong_notm}}](/docs/schematics?topic=schematics-getting-started) to manage the deployment.

## How do I estimate costs?
{: #what-is-project-cost}
{: faq}

You can view and estimate of starting costs for a variation of the deployable architecture from the {{site.data.keyword.cloud_notm}} catalog details page. When you deploy by using {{site.data.keyword.cloud}} projects, the starting costs for the project are estimated from the validation window after your changes to the configuration are saved and validated.

## How do I keep up with changes to my deployable architecture?
{: #what-is-notifications}
{: faq}

To make sure you stay up to date with the items that need attention in your deployable architecture, enable event notifications for projects. For more information, see [Enabling event notifications for projects](/docs/secure-enterprise?topic=secure-enterprise-event-notifications-events).
