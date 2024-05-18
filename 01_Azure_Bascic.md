# Cloud Computing and Azure

**Cloud computing** refers to delivering computing services like servers, storage, databases, networking, software, analytics, intelligence, and more over the internet.  You access these services on-demand, just like using electricity, without the need to manage physical infrastructure yourself. 

**Microsoft Azure** is one of the major cloud computing platforms, alongside Amazon Web Services (AWS) and Google Cloud Platform (GCP).  These platforms provide a wide range of services that businesses and individuals can leverage to build, deploy, and manage their applications and data centers. 

## What is Azure?
Azure is a **cloud computing platform created by Microsoft**. It offers solutions for computing, analytics, storage, and networking, among others. Azure provides infrastructure as a service (IaaS), platform as a service (PaaS), and software as a service (SaaS) offerings, enabling users to build, deploy, and manage applications and services with ease.

It offers a comprehensive set of cloud services that span:

* **Compute**: Virtual Machines for running any workload, serverless functions, containers, and more.
* **Storage**: Blob storage for unstructured data, file shares for collaboration, and databases like SQL Database and Cosmos DB.
* **Networking**: Virtual networks, firewalls, load balancers, and other tools to securely connect your resources.
* **Management**: Tools to provision, manage, and monitor your resources in the cloud.
* **AI & Machine Learning**: Services to build, deploy, and manage AI models.
* **Data Analytics**: Tools for storing, processing, analyzing, and visualizing your data.
* **Web & Mobile Development**: Services to build, deploy, and manage web and mobile applications.

### Azure Free Credits
Microsoft offers **free Azure credits** to help you get started with their cloud platform. This allows you to experiment with different services, deploy your own applications, and learn without any initial investment. Here's how to avail them:

* Visit the **Azure for Students** program: [https://azure.microsoft.com/en-us/free/students](https://azure.microsoft.com/en-us/free/students)
* Sign up with a valid student email address.
* You'll receive a credit amount to use for a limited duration (typically 1 year).

### Azure vs. Other Cloud Providers
While all major cloud providers offer similar core services, there are some key differences:

* **Focus**: Azure integrates well with other Microsoft products and services like Office 365 and Windows Server.  AWS has a wider range of services overall, and GCP is known for its strength in AI and machine learning.
* **Pricing**: Pricing models can vary depending on your specific needs. It's recommended to compare pricing structures for your chosen services across different providers.
* **Support**: All major providers offer comprehensive support options, but their specific offerings might differ. 
* Additionally, Azure boasts a global network of data centers, advanced AI capabilities through Azure AI, and strong support for hybrid cloud deployments.

### Advantages, Disadvantages, and Use Cases of Azure
#### Advantages of Azure
* **Scalability**: Easily scale resources up or down to meet changing demands.
* **Elasticity**: Ability to scale up or down dynamically.
* **Agility**: Ability to react quickly or to allocate and de-allocate the resources quickly.
* **Cost-effectiveness**: Pay only for what you use.
* **Security**: Robust security features and compliance certifications.
* **Reliability**: High availability and disaster recovery options.
* **Integration**: Integrates well with other Microsoft products and services.
* **AI**: Advanced AI capabilities.

> Note: 
> 1. Availability is the measure of system uptime for users or services.
> 2. High Availability is the ability to keep the services running for extended period of time with very little downtime.

#### Disadvantages of Azure
* **Vendor Lock-in**:  Relying heavily on Azure might make it difficult to switch to other providers in the future.
* **Complexity**: The vast array of services can be overwhelming for beginners.
* **Potential Costs**: Costs can add up quickly for resource-intensive workloads.

#### Use cases of Azure
* Developing and deploying web and mobile applications.
* Storing and analyzing big data.
* Creating and deploying machine learning models.
* Building and managing virtual machines and containers.
* Disaster recovery and backup solutions.
* Hosting websites and web applications.

### Free vs. Paid Services in Azure
**Free Services:** 
* Azure free account with limited usage for 12 months.
* Limited access to most services with restricted quotas (CPU, storage, etc.)
* Free tier includes tools for managing your resources and basic functionalities of core services.

**Paid Services:**
* Access to the full range of Azure services with higher quotas and scalability options.
* Pay-as-you-go pricing model based on your resource usage.
* Reserved instances and other options for predictable, lower costs for consistent workloads.


## What is Azure Portal?
The **Azure Portal** is a web-based, unified console provided by Microsoft to manage Azure resources and services. It offers a graphical user interface (GUI) that allows users to:
* Create, manage, and monitor Azure resources and services.
* Configure settings for various Azure services.
* Access billing information and manage subscriptions.
* Deploy applications and manage their configurations.
* Set up alerts and monitor the health and performance of resources.

The Azure Portal provides an integrated experience where users can perform almost all tasks related to their Azure environment without the need for extensive command-line or scripting knowledge.

## What is a Resource Group in Azure?
A **resource group** in Azure is a logical container that holds related Azure resources. These resources can include virtual machines, databases, storage accounts, web apps, and other services. Resource groups help organize resources and manage them collectively.

### Why do we first need to create a resource group before using any Azure service?
- **Organization**: Resource groups help organize resources logically, making it easier to manage and maintain them.
- **Lifecycle Management**: Resources within a resource group share the same lifecycle. For instance, if you delete a resource group, all resources contained within it are also deleted.
- **Access Control**: You can apply role-based access control (RBAC) at the resource group level, simplifying the management of permissions for multiple resources.
- **Billing and Monitoring**: Grouping resources allows for consolidated billing and monitoring, helping to track costs and performance more efficiently.

### How to Create a Resource Group in Azure?
You can create a resource group using the Azure Portal, Azure CLI, or PowerShell. Here's how to do it via the Azure Portal:

1. **Sign in to the Azure Portal**:
   - Navigate to [https://portal.azure.com](https://portal.azure.com) and sign in with your Azure account credentials.
2. **Navigate to Resource Groups**:
   - In the left-hand menu, click on "Resource groups".
3. **Create a New Resource Group**:
   - Click the "Create" button to start the creation process.
4. **Configure Resource Group Settings**:
   - **Subscription**: Select the Azure subscription you want to use.
   - **Resource group**: Enter a name for your resource group. The name must be unique within the Azure region.
   - **Region**: Select the Azure region where you want to create the resource group. The region determines where the metadata for the resource group will be stored.
5. **Review and Create**:
   - Review the settings you've configured. Click "Review + create" to validate the settings.
   - If everything looks good, click "Create" to create the resource group.