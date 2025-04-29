---

copyright:
  years: 2024
lastupdated: "2025-04-29"

keywords: security services, deployable architecture, IaC

subcollection: security-hub

---

{{site.data.keyword.attribute-definition-list}}


# What is cloud security?
{: #cloud-security}

At its core, cloud security is the collection of procedures and technology that is designed to address the potential threats that your organization might face as you include cloud-based tools and services as part of your infrastructure.
{: shortdesc}

Historically, security and compliance strategies have been time intensive and manual because when you deploy an application, you must manage the entire data center and servers, as well as the applications and data. In a cloud model, it's a shared responsibility between you and the cloud provider. As you get started on your journey to cloud, you must rethink your security architecture and fully understand what is your responsibility and what is the cloud providers.

Check out the following video to learn more about securely running your applications in the cloud.

![Video title](https://www.youtube.com/embed/jI8IKpjiCSM){: video output="iframe" data-script="#cs-video-transcript" id="youtubeplayer" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen}

## Video transcript
{: #cs-video-transcript}
{: notoc}

Hi, I'm Nataraj Nagaratnam and I'm from IBM Cloud. 

Traditionally when you deploy an application, you have the entire data center, the servers that you run - you're responsible for all of it. In the cloud model, that's a shared responsibility between you and the cloud provider. In a shared responsibility model, you need to rethink security on what your responsibility is and what the cloud provider's responsibility is.

Let's take platform-as-a-service (PaaS) as an example. When you look at PaaS, you're building applications, migrating data to the cloud and building applications running them on the cloud. So, you're responsible for securing the applications, the workload, and the data while the cloud provider is responsible for managing the security of the platform. So that it's compliant, it's secured from the perspective of network, the platform on down in terms of managing the containers and the runtime and isolation so that you have your own space within the platform.

Whereas if you are adopting and migrating workloads to the cloud and you're using infrastructure-as-a-service (IaaS), then the cloud provider manages the hypervisor on down if you are using virtual servers or, if you are using bare metal, then you can completely control everything on up from the operating system, the virtual servers that you run, and the data you bring it on.

So it's very important to understand the adoption model whether you're consuming IaaS or PaaS, or if you're consuming SaaS where the cloud provider manages all the applications and the security that is offered and you worry about the data that you bring in and plan accordingly. So that's a very important thing because it's part of understanding your
responsibility in ultimately managing the risk and compliance of the workloads of the data that you bring to the cloud.

Now let's talk about architecture.

When you build applications and migrate applications and modernize your apps - let's start with data. With all the risk that you deal with, and the kind of data matters. Is it confidential data, is it public data, or sensitive data that might deal with private information? Consider all those factors and make a secure design around what your data security architecture should be. Make sure you have data at rest encryption so that the data is always encrypted whether you use a database as a service, object store as a service, or other ways to store data like block storage. 

Encryption is for amateurs, and we think about key management for professionals. So having more control of your keys provide you with the ability in the context of shared responsibility model that you own your data and you have complete control of your data. So as you think about key management makes sure you have an approach to think about if you are bringing confidential data that you want to bring with your own keys might be sensitive data you want to keep your own keys. So that how much control of the keys you have and the hardware security module in which the key processing the encryption decryption operations happen more control you have more responsibility that you can take on. So encryption of data at rest, data in motion, as it comes from services to data stores or
applications so that as you think about data coming out of the way your requests and API requests coming all the way data in motion. And in the new world we need to start thinking about when the application is actually processing the data that is going to be data in its memory. So you can actually start to protect data that use hardware-based technologies where you can protect in-memory data as well. So that when it is in use and in memory by the applications you can protect it. 

So take a holistic approach to data protection at rest, in motion, in use with full control of your keys. It can be bring-your-own-keys, or even better push the boundary with keep your own keys. The application that serves the data it's not only about which application needs to have access make sure that the data access is on an only by need basis. Do not open up your data services to the whole world, be it network access or everybody to access the data, make sure you exactly know which applications need to access or which users need to access the data to run your cloud applications. From an application viewpoint make sure there are no vulnerabilities in your application so scan your applications, so I have an App SEC application security approach so that you can do dynamic scanning or static scanning of your application before you deploy it into the production, and in the cloud-native environment you're deploying container images so you can scan your images, you can scan it for vulnerabilities before you deploy and set your policies so that you only have secured images in production any time and if there is any vulnerability in the new world you don't need to patch these systems you just spin up a new container and off you go. That's the beauty of a cloud-native approach that you have security that is built in in every step. So at a container level and the applications that serve the business logic you can start to protect it. 

Then when you look at the users coming in you want to manage access in terms of who the user is and what from there they are coming from. So identity you need to make sure who the user is or which service it is based on the identity of those services or users so that you can manage access control to your application or data and also from the perspective of network access you want to make sure only authorized users can get in and if there are intruders out there you can make sure you can set it up so that they are prevented from accessing your application and your data in the cloud, be it through Web Application Firewall-ing, network access control or denial-of-service distributed, denial-of-service protection and have intelligence built into these network protection as well. So both identity and network. 

In essence, if you are protecting your data, you need to manage access to your apps and the workload on the data that you have deployed on the cloud. You need to have a continuous security monitoring so that you know at any point whether you're compliant to your policies, you can watch out for threats that you need to manage, having an approach and set of tools to manage security and complaints posture is very important. So gaining insights about your posture, compliance, and threats. So from your deployment environment you can garner information, it can be security events, audit logs, flow logs from network or system that can be fed in so that you can figure out what your posture and complaints and threats are, and that is not only important for you to gain insight you need to have actionable intelligence so that you can start to remediate. You might figure out there's a vulnerability, a container image that you have deployed is vulnerable so you can respin the container so you can remediate and spin up a new container. There might be a particular access from a network that seems to be coming in from a suspicious network IP address so we can block that. So the ability to gain visibility and insights and having that insights and turn it into actionable intelligence and remediate is very important. 

Let's talk about DevOps. DevOps is about development and operations. Traditionally we think about okay, there's an application team that is doing the design and architecture, who are building the code, and then you throw it over the wall for the enterprise security team to secure it and manage it. That should be rethought, fundamentally it's not just about Dev and Ops, but security need to be a forethought not an afterthought. So it should become a SecDevOps approach to the way you build, manage, and run your applications. So you need to embed security into the entire lifecycle, what we call `shift-left`, not only you manage security but `shift-left` through the entire process you need to have a secure design, so as you plan as you design and say what kind of data am I going to put what level of classification what kind of applications am I building, is it container-based, is it a workload that I'm migrating, take that into account and what integrations you need to do so that you can plan it and architect it. Then, as you build it embed security as part of that process. So you have security aware applications, for example you might want to encrypt data of your sensitive data, you might want to encrypt the data from your applications before you even you store into a data store. So secure build and you manage security as part of SecDevops as you have secure design and architecture you pass on that and build secure applications and deploy and manage security in a continuous fashion and then you have a closed loop so that whatever you find you might need to remediate or rearchitect your application or implement certain things as threats landscape evolve.

Thanks for watching this video. If you want to see more videos like it leave a comment, "like", and subscribe. Thank you.


## Understanding responsibilities
{: #responsibilities}

As explained in the previous video, cloud security responsibilities are highly dependent upon the type of cloud computing model that you're working with. See the following table to learn more.

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
