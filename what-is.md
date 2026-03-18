---

copyright:
  years: 2024
lastupdated: "2025-08-19"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}


# What is cloud security?
{: #cloud-security}

At its core, cloud security is the collection of procedures and technology that is designed to address the potential threats that your organization might face as you include cloud-based tools and services as part of your infrastructure.
{: shortdesc}

Historically, security and compliance strategies have been time intensive and manual because when you deploy an application, you must manage the entire data center and servers, as well as the applications and data. In a cloud model, it's a shared responsibility between you and the cloud provider. As you get started on your journey to cloud, you must rethink your security architecture and fully understand what is your responsibility and what is the cloud providers.

Check out the ![video](https://www.youtube.com/watch?v=jI8IKpjiCSM){: external} to learn more about securely running your applications in the cloud.






## Understanding responsibilities
{: #responsibilities}

As explained in the previous video, cloud security responsibilities are highly dependent upon the type of cloud computing model that you're working with. Check out the following table to learn more about the various types.

| Computing model | Description |
|------|-------------------------------------------------|
| Infrastructure-as-a-Service (IaaS) | Offers a hybrid approach, which allows organizations to manage some of their data and applications on-premises. At the same time, it relies on cloud providers to manage servers, hardware, networking, virtualization, and storage needs.|
| Platform-as-a-Service (PaaS) | Gives organizations the ability to streamline their application development and delivery. It does so by providing a custom application framework that automatically manages operating systems, software updates, storage, and supporting infrastructure in the cloud. |
| Software-as-a-Service (SaaS) | Provides cloud-based software hosted online and typically available on a subscription basis. Third-party providers manage all potential technical issues, such as data, middleware, servers, and storage. This setup helps minimize IT resource expenditures and streamline maintenance and support functions. |
{: row-headers}
{: caption="Responsibility by computing model" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the type of service being provided. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}


To learn more about the responsibilities by task, see [{{site.data.keyword.cloud_notm}} responsibilities](/docs/security-hub?topic=security-hub-shared-responsibilities). Additionally, if there are differences for a specific service, it is documented in that service documentation in a responsibilities topic.
{: tip}


## Understanding the challenges
{: #challenges}

While cloud security can never guarantee complete prevention of attacks and vulnerabilities, a well-designed strategy can go a long way toward preventing breaches or mitigating damage, improving compliance, and building stronger customer trust. It's important to recognize and understand the challenges that your organization might face as you work in a cloud environment. 

Two of the most important challenges to consider as you build your strategy are misconfiguration and compliance. Each year, misconfigurations within a cloud environment contribute to a high number of data breaches and can force your otherwise secure architecture out of compliance. But, with {{site.data.keyword.cloud_notm}}, you can work with predefined deployable architectures that help to automate infrastructure-as-code deployments and integrate security checks into everyday workflows to standardize and validate configurations across your environments, which can minimize your risk. 
