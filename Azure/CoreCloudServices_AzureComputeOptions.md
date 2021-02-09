Azure App Service is a platform-as-a-service (PaaS) offering in Azure that is designed to host enterprise-grade web-oriented applications.

Azure Virtual Machines (VMs) let you create and use virtual machines in the cloud. They provide infrastructure as a service (IaaS) in the form of a virtualized server 

you still need to maintain the VM—that is, configure, update, and maintain the software that runs on the VM.


### Scaling VMs in Azure

Availability sets
Virtual Machine Scale Sets
Azure Batc

An availability set is a logical grouping of two or more VMs that help keep your app available during planned or unplanned maintenance.

A planned maintenance event is when the underlying Azure fabric that hosts VMs is updated by Microsoft. A planned maintenance event is done to patch security vulnerabilities, improve performance, and add or update features. Most of the time these updates are done without any impact to the guest VMs. But sometimes VMs require a reboot to complete an update. When the VM is part of an availability set, the Azure fabric updates are sequenced so not all of the associated VMs are rebooted at the same time. VMs are put into different update domains. Update domains indicate groups of VMs and underlying physical hardware that can be rebooted at the same time. Update domains are a logical part of each data center and are implemented with software and logic.
Unplanned maintenance events involve a hardware failure in the data center, such as a server power outage or disk failure. VMs that are part of an availability set automatically switch to a working physical server so the VM continues to run. The group of virtual machines that share common hardware are in the same fault domain. A fault domain is essentially a rack of servers. It provides the physical separation of your workload across different power, cooling, and network hardware that support the physical servers in the data center server racks. In the event the hardware that supports a server rack becomes unavailable, only that rack of servers is affected by the outage.

With an availability set, you get:

Up to three fault domains that each have a server rack with dedicated power and network resources.
Five logical update domains which then can be increased to a maximum of 20.


There's no cost for an availability set. You only pay for the VMs within the availability set. We highly recommend that you place each workload in an availability set to avoid having a single point of failure in your VM architecture.

### virtual machine scale sets

Azure Virtual Machine Scale Sets let you create and manage a group of identical, load balanced VMs. 


Scale sets allow you to centrally manage, configure, and update a large number of VMs in minutes to provide highly available apps. The number of VM instances can automatically increase or decrease in response to demand or a defined schedule. With Virtual Machine Scale Sets, you can build large-scale services for areas such as compute, big data, and container workloads

### Azure Batch

Azure Batch enables large-scale job scheduling and compute management with the ability to scale to tens, hundreds, or thousands of VMs.

When you're ready to run a job, Batch does the following:

Starts a pool of compute VMs for you
Installs apps and staging data
Runs jobs with as many tasks as you have
Identifies failures
Requeues work
Scales down the pool as work completes
There may be situations in which you need raw computing power or supercomputer level compute power. Azure provides these capabilities.

#### Containers in Azure
Azure supports Docker containers (a standardized container model), and there are several ways to manage containers in Azure.

1. Azure Container Instances (ACI)
2. Azure Kubernetes Service (AKS)


#### Azure Container Instances
Azure Container Instances (ACI) offers the fastest and simplest way to run a container in Azure. You don't have to manage any virtual machines or configure any additional services. It is a PaaS offering that allows you to upload your containers and execute them directly with automatic elastic scale.


#### Azure Kubernetes Service
The task of automating, managing, and interacting with a large number of containers is known as orchestration. Azure Kubernetes Service (AKS) is a complete orchestration service for containers with distributed architectures with multiple container

#### Migrating apps to containers

You can move existing applications to containers and run them within AKS. In the cluster, you can use Azure Service Operator (ASO) to control access to Service Level Agreement (SLA)–backed Azure services, such as Azure Database for MySQL. ASO makes use of the AKS cluster-managed identity for authentication when accessing Azure resources.

You can move existing apps to containers and run them within AKS. You can control access via integration with Azure Active Directory (Azure AD) and access Service Level Agreement (SLA)–backed Azure services, such as Azure Database for MySQL for any data needs, via Azure Service Operator (for Kubernetes).

![azure img](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-compute/media/4-kub-migration.png)


The preceding figure depicts this process as follows:

You convert an existing app to one or more containers and then publish one or more container images to the Azure Container Registry.
By using the Azure portal or the command line, you deploy the containers to an AKS cluster.
Azure AD controls access to AKS resources.
You access SLA-backed Azure services, such as Azure Database for MySQL, via Azure Service Operator (for Kubernetes).
Optionally, AKS is deployed with a virtual network.
With ASO, Kubernetes manifests can provision an Azure Database for MySQL on your behalf.

#### Azure App Service

Azure App Service enables you to build and host web apps, background jobs, mobile backends, and RESTful APIs in the programming language of your choice without managing infrastructure. It offers automatic scaling and high availability. App Service supports both Windows and Linux, and enables automated deployments from GitHub, Azure DevOps, or any Git repo to support a continuous deployment model.
This platform as a service (PaaS) allows you to focus on the website and API logic while Azure handles the infrastructure to run and scale your web applications.

#### Types of app services

With Azure App Service, you can host most common app service styles, including:

1. Web Apps
2. API Apps
3. WebJobs
4. Mobile App

#### Serverless computing

Serverless computing is the abstraction of servers, infrastructure, and OSs. With serverless computing, Azure takes care of managing the server infrastructure and allocation/deallocation of resources based on demand. Infrastructure isn't your responsibility. Scaling and performance are handled automatically, and you are billed only for the exact resources you use. There's no need to even reserve capacity.

Serverless computing encompasses three ideas: the abstraction of servers, an event-driven scale, and micro-billing:

1. Abstraction of servers: 

Serverless computing abstracts the servers you run on. You never explicitly reserve server instances; the platform manages that for you. Each function execution can run on a different compute instance, and this execution context is transparent to the code. With serverless architecture, you simply deploy your code, which then runs with high availability.

2. Event-driven scale:

Serverless computing is an excellent fit for workloads that respond to incoming events. Events include triggers by timers (for example, if a function needs to run every day at 10:00 AM UTC), HTTP (API and webhook scenarios), queues (for example, with order processing), and much more. Instead of writing an entire application, the developer authors a function, which contains both code and metadata about its triggers and bindings. The platform automatically schedules the function to run and scales the number of compute instances based on the rate of incoming events. Triggers define how a function is invoked and bindings provide a declarative way to connect to services from within the code.
 
3. Micro-billing:

Traditional computing has the notion of per-second billing, but often, that's not as useful as it seems. Even if a customer's website gets only one hit a day, they still pay for a full day's worth of availability. With serverless computing, they pay only for the time their code runs. If no active function executions occur, they're not charged. For example, if the code runs once a day for two minutes, they're charged for one execution and two minutes of computing time.

Azure has two implementations of serverless compute:

1. Azure Functions, which can execute code in almost any modern language.
2. Azure Logic Apps, which are designed in a web-based designer and can execute logic triggered by Azure services without writing any code.
 
 #### Azure Functions
 
 Azure Functions scale automatically based on demand, so they're a solid choice when demand is variable.
 With functions, Azure runs your code when it's triggered and automatically deallocates resources when the function is finished. In this model, you're only charged for the CPU time used while your function runs.
 Furthermore, Azure Functions can be either stateless (the default), where they behave as if they're restarted every time they respond to an event, or stateful (called "Durable Functions"), where a context is passed through the function to track prior activity.
 If the needs of the developer's app change, you can deploy the project in an environment that isn't serverless, which provides the flexibility to manage scaling, run on virtual networks, and even completely isolate the functions.
 
 #### Azure Logic Apps
 
 Azure Logic Apps are similar to Functions - both enable you to trigger logic based on an event. Where Functions execute code, Logic Apps execute workflows designed to automate business scenarios and built from predefined logic blocks.
 Every logic app workflow starts with a trigger, which fires when a specific event happens or when newly available data meets specific criteria. Many triggers include basic scheduling capabilities, so developers can specify how regularly their workloads will run. Each time the trigger fires, the Logic Apps engine creates a logic app instance that runs the actions in the workflow. These actions can also include data conversions and flow controls, such as conditional statements, switch statements, loops, and branching.
 You create Logic App workflows using a visual designer on the Azure portal or in Visual Studio. The workflows are persisted as a JSON file with a known workflow schema.

Azure provides over 200 different connectors and processing blocks to interact with different services - including most popular enterprise apps. You can also build custom connectors and workflow steps if the service you need to interact with isn't covered. You then use the visual designer to link connectors and blocks together, passing data through the workflow to do custom processing - often all without writing any code.

As an example, let's say a ticket arrives in ZenDesk. You could:

Detect the intent of the message with cognitive services
Create an item in SharePoint to track the issue
If the customer isn't in your database, add them to your Dynamics 365 CRM system
Send a follow-up email to acknowledge their request
All of that could be designed in a visual designer making it easy to see the logic flow, which is ideal for a business analyst role.

#### Functions vs. Logic Apps

Functions and Logic Apps can both create complex orchestrations. An orchestration is a collection of functions or steps, that are executed to accomplish a complex task. With Azure Functions, you write code to complete each step, with Logic Apps, you use a GUI to define the actions and how they relate to one another.


 