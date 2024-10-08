---

copyright:
  years: 2024
lastupdated: "2024-10-08"

keywords: security services, deployable architecture, IaC

subcollection: security-services

---

{{site.data.keyword.attribute-definition-list}}

# Overview of the {{site.data.keyword.name-da}} deployable architecture
{: #overview}

The {{site.data.keyword.name-da}} deployable architecture is a preconfigured set of infrastructure as code (IaC) assets that are deployed and configured based on the recommended best practices. {{site.data.keyword.cloud_notm}}'s core security services are crucial for ensuring robust security and compliance for cloud-based applications and data. The primary goal is to provide a framework for secure and compliant {{site.data.keyword.cloud_notm}} workloads.

This deployable architecture is designed to showcase a fully automated deployment of {{site.data.keyword.cloud_notm}} core security services and its dependencies through {{site.data.keyword.cloud_notm}} Project, providing a flexible and customizable foundation for your own application deployments on {{site.data.keyword.cloud_notm}}.

By leveraging this architecture, you can accelerate your deployment and tailor it to meet your unique business needs and enterprise goals.

By using this architecture, you can:



* **Ensure observability:** The architecture provides observability by deploying services such as {{site.data.keyword.la_full_notm}}, {{site.data.keyword.monitoringlong_notm}}, {{site.data.keyword.atracker_full_notm}}, {{site.data.keyword.en_full_notm}}, and log retention through {{site.data.keyword.cos_full_notm}} buckets.
* **Implement security:** The architecture ensures security by deploying {{site.data.keyword.keymanagementservicelong_notm}} and {{site.data.keyword.secrets-manager_full_notm}}.
* **Achieve regulatory compliance:** The architecture ensures regulatory compliance by implementing centralized key management, centralized secrets management, and along with {{site.data.keyword.sysdigsecure_full_notm}}, secure application lifecycle management.

## Features and capabilities
{: #overview-features}

This deployable architecture supports these features.

* Creates and configures a {{site.data.keyword.keymanagementserviceshort}} instance and creates root keys for {{site.data.keyword.cos_full_notm}}, {{site.data.keyword.en_short}}, and {{site.data.keyword.secrets-manager_short}}.
* Creates and configures an {{site.data.keyword.secrets-manager_short}} instance.
* Creates and configures an IBM Security Compliance Center instance.
* Creates and configures an {{site.data.keyword.sysdigsecure_full_notm}} instance.
* Creates and configures an {{site.data.keyword.cos_full_notm}} instance and multiple {{site.data.keyword.cos_short}} buckets that are encrypted by {{site.data.keyword.keymanagementserviceshort}}.
* Creates and configures service-to-service authorizations for the following services: KMS, {{site.data.keyword.en_short}}, {{site.data.keyword.cos_short}}, {{site.data.keyword.secrets-manager_short}}, and Security and Compliance Center.
* Creates and configures IBM Observability components {{site.data.keyword.atracker_short}}, {{site.data.keyword.monitoringlong_notm}}, and {{site.data.keyword.loganalysislong_notm}}.
* Ensures compliance with some of the controls in the CIS IBM Cloud Foundations Benchmark profile. To view the list of added controls, follow these steps:
    1.  Go the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external} and search for the {{site.data.keyword.name-da}} deployable architecture.
    1.  Click the tile for the deployable architecture to open the details. The Security & compliance tab lists all of the controls that are included in the deployable architecture.
