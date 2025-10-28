---
# try also 'default' to start simple
theme: default
presenter: true
title: 'Cloud Computing Fundamentals'
titleTemplate: '%s - CPIT-490'
# apply any windi css classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: | 
    Cloud Computing Fundamentals
# page transition
transition: slide-left
# use UnoCSS
css: unocss
# Make content selectable/copyable
selectable: true
favicon: '/images/favicon.ico'
# Make slides downloadable as PDF
download: true
exportFilename: cloud-computing-slides
export:
  format: pdf
  timeout: 50000
  dark: false
  withClicks: false
  withToc: true
# enable slide recording and drawing
record: build
drawings:
  enabled: true
  persist: false
  presenterOnly: false
  syncAll: true
---

# Cloud Computing Fundamentals

### CPIT-490/632: Cloud Computing Architecture


<div class="absolute left-30px bottom-30px">
Spring 2024 &copy; Khalid Alharbi, Ph.D.
</div>

---

# Table of Contents
- What's Cloud Computing
- Evolution of Cloud Computing
- Cloud Deployment Models
- Cloud Service Models
- Cloud Storage
- Architectural Choices


---
layout: center
---

# What's Cloud Computing?
> "Cloud computing is a model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (e.g., networks, servers, storage, applications, and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction." [^1]

[^1]: <small>[The NIST Definition of Cloud Computing (NIST Special Publication 800-145)](https://csrc.nist.gov/publications/detail/sp/800-145/final)</small>


---
layout: center
---


# The Evolution of Cloud Computing

<div style="display: flex; justify-content: space-around;">
  <div style="width: 20%; border: 1px solid; border-radius: 15px; padding: 5px; margin: 5px;">
    <h4 style="font-weight: bold; padding-bottom: 10px;">Traditional Data Center</h4>
    <ul style="font-size: 0.8em;">
      <li>Terminals</li>
      <li>Multiple distributed servers</li>
      <li>Large individual servers</li>
    </ul>
  </div>
  <div style="width: 20%; border: 1px solid; border-radius: 15px; padding: 10px; margin: 10px;">
    <h3 style="font-weight: bold; padding-bottom: 10px;">Server Virtualization</h3>
    <ul style="font-size: 0.8em;">
      <li>Virtual instances of IT resources (compute, storage, networking, etc.)</li>
      <li>Type-1 Hypervisors (e., Xen, Vmware ESXi)</li>
    </ul>
  </div>
    <div style="width: 20%; border: 1px solid; border-radius: 15px; padding: 10px; margin: 10px;">
    <h3 style="font-weight: bold; padding-bottom: 10px;">Private Cloud/On-premise / Internal Corporate Cloud</h3>
    <ul style="font-size: 0.8em;">
      <li>Managed by a single organization</li>
      <li>Offered to select users</li>
      <li>Often used due to regulatory reasons</li>
    </ul>
  </div>
    <div style="width: 20%; border: 1px solid; border-radius: 15px; padding: 10px; margin: 10px;">
    <h3 style="font-weight: bold; padding-bottom: 10px;">Hybrid Cloud</h3>
    <ul style="font-size: 0.8em;">
      <li>A combination of a private cloud and a public cloud</li>
    </ul>
  </div>
    <div style="width: 20%; border: 1px solid; border-radius: 15px; padding: 10px; margin: 10px;">
    <h3 style="font-weight: bold; padding-bottom: 10px;">Public Cloud</h3>
    <ul style="font-size: 0.8em;">
      <li>IT resources and services offered by third-party provides over the public internet (off-premise)</li>
      <li>Examples: AWS, Azure, and GCP</li>
    </ul>
  </div>
</div>



---
layout: center
---

# Cloud Deployment Models
- Private Cloud
- Community Cloud
- Public Cloud
- Hybrid Cloud

---

# Private Cloud
- An internal cloud that’s hosted on-premises and owned by a single - organization.


### Pros:

<div v-click>

- Full control over management and data
- Controlled level of security
- Controlled level of privacy

</div>

### Cons:

<div v-click>

- Complex and expensive operations and maintenance costs.
- Security depends on staff expertise
- Slow integration and restricted access

</div>

---

# Community Cloud

- A cloud that’s shared among multiple organizations in a shared community.
- Examples: research labs, health care companies, financial companies, etc.
### Pros:
<div v-click>

- Controlled level of security and privacy.
- Meeting regulatory compliance requirements.
- Cost may be shared among participants.
</div> 

### Cons:

<div v-click>

- Similar to the limitations of private clouds
</div>

---

# Public Cloud
- A cloud that’s hosted and owned by a 3-rd party, cloud provider.
- Examples: AWS, Azure, GCP

### Pros:

<div v-click>

- Scalability
- Lower costs
- Enterprise-level support
- Faster integration
- Upgrades and maintenance
- Security and reliability

</div>

### Cons:

<div v-click>

- Privacy and regulatory compliances

</div>


---

# Hybrid Cloud

- A cloud that combines a private or on-premise cloud with a public cloud.

### Pros:

<div v-click>

- Cost effective
- Regulatory compliances
- Full control over sensitive assets.

</div>

# Cons:


<div v-click>

- Security depends on staff expertise
- Integration between clouds introduces additional complexity

</div>

---
layout: center
---

# Characteristics of Cloud Computing

- On-demand self service
- Broad network access
- Resource pooling
- Resource utilization through virtualization
- Rapid elasticity
- Metered services

---

# On-demand Self Service
- The ability for users to provision compute resources whenever needed, without requiring human interaction with the service provider.
- Users can manage and adjust their usage and spending to meet their requirements.
- Services can be scaled up, down, out or in based on demand, providing flexibility and scalability.
<div v-click>

  - **Vertical Scaling**: up or down
    - **Scaling Up**: Increasing the capacity of a single server by adding more resources like CPU, memory, or storage often in response to increased demand.
    - **Scaling Down**: Reducing the resources of a single server like CPU, memory, or storage, often in response to decreased demand.

</div>

<div v-click>

  - **Horizontal Scaling**: out or in
    - **Scaling Out**: Adding more servers/VMs to distribute the load among them, improving performance and availability.
    - **Scaling In**: Reducing servers/VMs when they are no longer needed, typically due to decreased load or demand.

</div>

---

# Broad Network Access

- Services are available over the network and accessed through common networking protocols.
- Remote access to compute and storage resources and services.
- Remote management to cloud resources
- Complete networking control by the user, allowing for custom network configurations, security settings, and other network management tasks.
- Integration with multiple services and platforms maintained by different vendors.

---

# Resource Pooling

- Compute and storage resources are made available and can be provisioned and assigned to any user.
- Cloud providers server different users (tenants) ensuring that the resources of each tenant are isolated from others. This term is referred to as multitenancy.
- Physical and virtual compute and storage resources dynamically assigned and reassigned to users.
- Resources are pooled across multiple customers (multi-tenancy environmant) and can be assigned or reassigned to each customer based on demand.

---

# Resource Utilization Through Virtualization
- Cloud computing improves the resource utilization through virtualization of compute, storage, and network resources.
- Virtualization abstracts the underlying physical resources allowing for better utilization of resources for cloud providers and their customers.
  - **Virtual compute resources**: such as virtual machines, and containers with the underlying hardware capabilities provided in virtual environment in the form of virtual CPUs and virtual memories that abstract the underlying physical CPU and memory.
   - **Virtual storage resources**: such as virtual disks, and storage devices that abstract the underlying physical storage hardware and capabilities.
    - **Virtual network resources**: such as virtual networks, subnets, and virtual private clouds that provide isolated and secure environments for all compute and storage resources. 


---

# Rapid Elasticity
- Elasticity denotes the ability to dynamically expand or reduce compute and storage resources to meet the evolving needs of an application.
- The ability to quickly scale out (add more servers) or scale in (remove servers) resources as demand changes and often automatically.
- Resources can be provisioned and released to dynamically adjust to workload changes.
- This elasticity allows for cost efficiency, as users only pay for the resources they use.
- It enables applications to handle peak loads without being restricted to  capacity limitations.
- Rapid elasticity can be achieved manually, scheduled based on predictable patterns, or automatically through autoscaling based on demand.

---

# Metered Services
- Metered services in cloud computing is a pricing model based on **pay-per-use**, in which customers are charged based on their usage of the service or provisioning of resources.
- This model provides transparency for both cloud providers and users.
- The use of compute, storage, and network resources or services is measured and billed according to usage.
- Usage is typically measured in terms of computing hours, storage, bandwidth, network ingress or egress, or number of processed requests.
- It allows for better utilization and optimization of resources, as users can monitor their usage.
- The pricing model can also be influenced by geographical factors, such as the region where the services are deployed, due to variations in operational costs across different locations.


---
layout: center
---

# Cloud Service Models

- Software as a Service (SaaS)
- Platform as a Service (PaaS)
- Infrastructure as a Service (IaaS)
- Function as a Service (FaaS)


---

# Software as a Service (SaaS)

- A software that can be used over the Internet, eliminating the need for users to install, run and maintain applications.
- SaaS represents a complete solution where all underlying infrastructures, - runtime environments, and storage are managed by the provider.
- Users can access the software and its functions remotely anywhere on client applications.
- The service provider manages the hardware, software, availability, security, and provides support to their users.
- SaaS is typically based on a subscription model, where users pay a regular fee to use the software, or on pay-as-you-go basis.
- Examples: Microsoft Office 365, Google Workspace, Blackboard, MS Teams, Amazon Chime, etc.

---

# Platform as a Service (PaaS)

- Platform as a Service (PaaS) is a cloud computing service model that offers a complete development and deployment environment. 
- It essentially provides a platform for developers to build and run their applications without managing the underlying infrastructure.
- Developers can create applications using the cloud provider's out of the box development framework and tools and run them in a pre-configured environment.
- Developers can deploy and ship applications without adding staff (e.g., Site-reliability/DevOps engineers) since all servers, storage, and networking are managed by the provider.
- Fully integrated environment for building, testing, deploying, managing, and updating applications.
- Compute resources can be scaled up or down to match demand so you pay for what you use.
- Examples: Google App Engine, AWS Elastic Beanstalk, and Azure App Service, and Heroku.
  - Notable applications: Khan Academy and Snapchat
    - Snapchat was built on Google App Engine until 2020. [<sup><small>[source](https://eng.snap.com/monolith-to-multicloud-microservices-snap-service-mesh)</small></sup>].


---

# Infrastructure as a Service (IaaS)

- Infrastructure as a Service (IaaS) is a cloud computing service model that provides on-demand access to low-level computing resources. 
- Cloud providers offer provisioning compute, storage, and network resources on a pay-as-you-go basis.
- Offers the flexibility to scale the required resources up and down to meet demands.
- Users can provision, configure, and manage their own infrastructure including compute, storage, network, operating systems, middleware, and services.
- Examples: Amazon AWS, Microsoft Azure, and Google GCP.

---

# Function as a Service (FaaS) (I)
- Function as a Service (FaaS) is a cloud computing service model that allows developers to build, deploy, and run serverless functions. 
- This is latest and most innovative cloud computing service model
- FaaS is designed to execute small pieces of code (functions) in response to events.
- Developers don't have to worry about managing servers, virtual machines, or underlying infrastructure.
- The cloud provider runs the server and dynamically manages the resources required to run the application or scale the resources on their infrastructure instantly to meet the demand.
- Despite the "serverless" name, servers are still running the code but not managed by the user.
- In FaaS, functions are stateless and short-lived.
  - Stateless functions do not retain memory or keep values from their previous executions.
  - If a function is idle or not executing code, it may be timed out by the cloud provider.


---

# Function as a Service (FaaS) (II)
- FaaS is a good fit for applications that respond to events, need to scale quickly, have variable demand, or are composed of microservices. 
- It's particularly useful for applications that perform some processing and then exits, storing the results in a storage service. 
  - Examples: Data processing tasks, image resizing, video transcoding, microservices (payment processing, fraud detection, shipping handling services) ,etc.
- However, FaaS may not be a good fit for applications that require long-running, stateful sessions or have complex application architectures.
  - Examples: Web servers, database systems, real-time communication applications such as  video conferencing tools, chat applications, etc.


---

# Function as a Service (FaaS) (III)

- Usage-based payment model: pay for the resources used while executing your code.
  - Pricing is based on the actual amount of resources consumed by an application, rather than on provisioned resources and pre-purchased units of capacity in other service models.
  - It's often cost-effective as you only pay for the resources your functions use while they're running.
- Examples: AWS Lambda, Azure functions, and GCP Cloud Functions.
  - AWS Lambda was the first FaaS offering by a large public cloud vendor.

---
layout: full
---

![](/images/saas-paas-faas-iaas.svg)

---
layout: two-cols
---

# PaaS vs FaaS

- Both PaaS and FaaS share the following similarities:
  - Focus on writing application and business logic instead of operation and deployment
  - Operational overhead is eliminated: No server or infrastructure management 
- Despite the similarities between PaaS and FaaS, they have distinct differences.

::right::
- **PaaS**
  - Full Control over deployment environment
  - Auto scaling must be configured
  - App is always running and executing
  - Deployment time is longer due to provisioning resources

**FaaS**
- Less Control over deployment environment.
- Auto scaling is often pre-configured.
- Code is only executed when an event is triggered.
- Deployment time is shorter since the infrastructure is completely abstracted
- Application exits upon completion of execution or timeout.

---

# Cold Start Problem in FaaS
- Functions are often executed in a linux container
  - A Linux container is similar to a VM, but more lightweight and faster to start up than VM.
  - Instead of creating a whole VM with a host operating system, a container allows applications to run in an isolated environment sharing the host system's OS kernel.
- When a function hasn't been executed recently, the container is likely not running and this will result in a noticeable delay in the first execution
- This is known as the "cold start" problem.
- This means when a new event is triggered to execute the function, the FaaS platform needs to locate a running Linux container, download your function code, initialize the runtime environment, and then finally execute your code.
- Cloud providers offer several solutions to mitigate the cold start problem and keep the function "warm" (initialized and ready to respond in double-digit milliseconds).

---
layout: center
---
# Cloud Computing Concepts
Key concepts in cloud computing and data centers

---

# Regions and Availability Zones

- **Regions**: A region is a physical location around the world where data centers are clustered in multiple physically isolated groups called availability zones.
- **Availability Zones (AZs)**: An Availability Zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.
- **Edge Networks**: Edge locations are connected to the AWS Regions through the AWS network backbone that circles the globe.

---

##  Virtual Private Server VPS
- A virtual private server (VPS), is a virtual machine (VM) running on a physical server in the cloud, which is owned and operated by a cloud provider.
- The term "instance" or "VM instance" is often used in cloud computing to refer to a virtual server.
- A Virtual Private Server (VPS) uses an image as a template to create a new instance or virtual machine. 
- When you create a VM instance in the cloud, you select an image that the instance uses to boot.
- VPSs or VM instances are priced much lower than an actual physical server, but as they share the underlying physical hardware with other VPSs.
  - As a result, the performance may be lower,when running on a shared server with a higher workload of other VM instances on the same hardware node.

---

# VPS Cloud Tenancy (I)
There are primarily two types of cloud tenancy for a Virtual Private Server (VPS) on the cloud:

- **Shared Tenancy - Default**: Multiple tenants (customers) share the same physical hardware. Each tenant's VPS is isolated from the others, but they all run on the same physical server. This is the default tenancy and is cheaper than dedicated tenancy.

- **Dedicated Tenancy**: A single tenant (customer) occupies an entire physical server. This means that all the resources of that server are dedicated to that one tenant's VPSs. This is more expensive than shared tenancy.

---

# VPS Cloud Tenancy (II)
- Some cloud providers such as AWS offer two types of dedicated tenancy: **dedicated hosts** and **dedicated instances**:
  - **Dedicated hosts**: This is a physical server with VM instance capacity fully dedicated to a single customer.
    - If you stop and start the VM instance, it will always run on the same physical server you're paying for. Billing os per host
  - **Dedicated instances**: These are VM instances that run on hardware that's dedicated to a single customer. 
    - Every time you stop and start the VM instance, it may run on different physical dedicated server that is not shared with others. Your instance is running in a dedicated hardware but not locked down to your account as it moves around on different physical servers not shared with others. Billing is per instance.

---

# VPS Pricing in the Cloud (I)

- Pricing for VPS in the cloud is typically based on the resources allocated, such as CPU, memory, storage, and network resources and egress.
- Pricing can be based on how you provision the VPS instances whether on-demand, reserved instances, or spot instances:
  - **On-Demand Pricing:** for provisioning VM instances on demand 
  - **Reserved Instances:** for reserving VM instances for a long term contact.
  - **Spot Instances**: for bidding on instances and handling workloads that can tolerate interruptions due to eviction

---
layout: center
---

## On-Demand Pricing
  - Pay per hour (or sometimes per minute) for the resources you use.
  - Most flexible option, ideal for workloads with unclear resource requirements.
  - Generally the most expensive pricing model per hour

---
layout: center
---

## Reserved Instances
  - Purchase resources (VPS instances) in advance for a fixed term (usually 1 or 3 years) at a discounted rate compared to on-demand pricing.
  - Offers significant cost savings if you have predictable workloads.
  - Less flexible, as you're locked into a specific instance type and region for the reserved term.
  - Some cloud providers allow you to sell unused the remaining of your reserved term to other customers in a marketplace, should you no longer need them.

---
layout: center
---

## Spot Instances
  - Customers bid on unused compute capacity from the cloud provider at significantly lower prices (up to 90% discount) compared to on-demand pricing.
  - Most cost-effective option, but comes with the risk of interruption if the spot price increases or the underlying capacity is needed by the cloud provider.
  - Customers may be evicted but will be notified to move the workload onto another VM instance.
  - Best suited for workloads that are fault-tolerant and can be restarted if interrupted for eviction.

---


# Auto Scaling

- Autoscaling refers to dynamically adjusting the amount of computational resources in a server farm based on the actual workload and demand
- Autoscaling: Scale up and down automatically with little operational overhead.
- Example: increase or decrease the number of VM instances running behind a web application automatically based on the number of active users on the web application.
- This solves poor capacity decisions such as over-provisioning and under-provisioning.
  - **over-provisioning**: The allocation of more resources than are actually needed. Although performance may not be an issue with over-provisioning resources, it will lead to unnecessary costs.
  - **under-provisioning**: The allocation of fewer resources than are actually needed. Although it can save costs, it will lead to performance issues or even service outages.

---

# Infrastructure as Code (IaC)

- Infrastructure as Code (IaC) is the practice of provisioning or allocating computing infrastructure and resources through source code that can be read and understood by machines, instead of using interactive tools such as the web portal or console or CLI tools.
- IaC can simplify the process of managing servers and help ensure consistency, repeatability, and reliability.
- Examples: AWS CloudFormation, Google Cloud Deployment Manager, Azure Resource Manager, Terraform, and Ansible.


---

# Infrastructure as Code (IaC) Example:

Example of using Terraform to provision a VM with an Apache web server on Azure:

*create_vm.tf*

```terraform {1-90}{maxHeight:'70%'}
provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "rg" {
  name     = "myResourceGroup"
  location = "West US"
}

resource "azurerm_virtual_network" "vnet" {
  name                = "myVNet"
  address_space       = ["10.0.0.0/16"]
  location            = azurerm_resource_group.rg.location
  resource_group_name = azurerm_resource_group.rg.name
}

resource "azurerm_subnet" "subnet" {
  name                 = "mySubnet"
  resource_group_name  = azurerm_resource_group.rg.name
  virtual_network_name = azurerm_virtual_network.vnet.name
  address_prefixes     = ["10.0.1.0/24"]
}

resource "azurerm_network_interface" "nic" {
  name                = "myNIC"
  location            = azurerm_resource_group.rg.location
  resource_group_name = azurerm_resource_group.rg.name

  ip_configuration {
    name                          = "myNICConfg"
    subnet_id                     = azurerm_subnet.subnet.id
    private_ip_address_allocation = "Dynamic"
  }
}

resource "azurerm_linux_virtual_machine" "vm" {
  name                = "myVM"
  location            = azurerm_resource_group.rg.location
  resource_group_name = azurerm_resource_group.rg.name
  network_interface_id = azurerm_network_interface.nic.id
  size                = "Standard_B2s"

  os_disk {
    caching              = "ReadWrite"
    storage_account_type = "Standard_LRS"
  }

  source_image_reference {
    publisher = "Canonical"
    offer     = "UbuntuServer"
    sku       = "16.04-LTS"
    version   = "latest"
  }

  computer_name  = "myvm"
  admin_username = "azureuser"
  disable_password_authentication = true

  admin_ssh_key {
    username   = "azureuser"
    public_key = file("~/.ssh/id_rsa.pub")
  }

  custom_data = base64encode(data.template_file.init.rendered)
}

data "template_file" "init" {
  template = file("init.tpl")

  vars = {
    hostname = azurerm_linux_virtual_machine.vm.name
  }
}
```

---

# General Cloud Design Principles
- **Anticipate failure**: Instead of treating failure as an unusual event, it should be considered as a normal operational event.
- **Design for resiliency**: Resiliency needs to be used in all layers of architecture: infrastructure, application, database, security, and networking.
- **Design high availability and fault tolerant solution**:
  - **Availability** refers to the percentage uptime of a particular resource in 9s.
  - **High Availability** means the system is up and available, but it might perform in degraded state.
  - **Fault tolerance** is a higher version of High Availability and means the system will continue to function without degradation in performance despite the complete failure of component(s).

---

# Common Application Availability Design Goals (I)

- **Service-Level Agreement (SLA)** is an agreement between a service provider and a customer and contains the availability of a resource in term of "9s".
- The term "9s" refers to the number of nines in the percentage.
- Two Nines: 99% availability means the resource may be unavailable for approximately 3.65 days per year or 7.20 hours per month or 1.68 hours per week. This is calculated as the remaining 1% of the time in a year, month, or week respectively.
- In the event a cloud provider does not meet the uptime specified in the SLA, you will be eligible to receive a service credit or refund.
- Example: [Amazon Compute Service Level Agreement for EC2, the virtual machine service)](https://aws.amazon.com/compute/sla/.

---

<style>
table {
  font-size: 0.8em;
}
</style>

# Common Application Availability Design Goals (I)I
- Below is  is a table of common application availability design goals and the maximum length of time that interruptions can occur within a year while still meeting the goal and examples of application types that may be suitable to operate within each availability tier [^1]

| Availability | Maximum Unavailability per Year | Application Category |
|--------------|---------------------------------|----------------------|
| 90% (One Nine) | 36.5 days | Non-critical applications, development environments |
| 99% (Two Nines) | 3.65 days | Batch processing, data extraction, transfer, and load jobs |
| 99.9% (Three Nines) | 8.76 hours | Internal tools like knowledge management, project tracking |
| 99.99% (Four Nines) | 52 minutes | Online commerce, point of sale, Video delivery, broadcast workloads |
| 99.999% (Five Nines) | 5 minutes | Critical applications, financial transactions, ATM, telecommunications workloads |

[^1]: [AWS Well-Architected Framework - Availability](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/availability.html)

---
layout: two-cols
---


<style>
table {
  font-size: 0.8em;
}
</style>

# AWS Services

| AWS Service | Availability |
|-------------|------------------|
| EC2         | 99.99%           |
| S3          | 99.99%           |
| RDS         | 99.95%           |
| Lambda      | 99.95%           |
| EBS         | 99.99%           |
| ELB         | 99.99%           |

::right::

# Azure Services

| Azure Service | Availability |
|---------------|------------------|
| Virtual Machines | 99.9% - 99.99% |
| App Service | 99.95% |
| Azure Functions | 99.95% |
| SQL Database | 99.99% |
| Storage Accounts | 99.9% - 99.99% |
| Azure Kubernetes Service | 99.95% |

---

# Availability Design Goal Example: 99%
- Consider the following scenario where a VM failed in one availability zone (AZ) and calculate an availability design goal of **99%**.
<div v-click>

- **30 minutes** to understand what went wrong and decide how to execute recovery.

</div>
<div v-click>

- **10 minutes** to deploy the whole stack in IaC, assume that we deploy to a new availability zone (AZ)
- **30 minutes** to restore the database
</div>

<div v-click>

- In total, that’s 70 minutes to recover from a failure.

</div>

<div v-click>

  - One failure per quarter => 4 * 70 = **280 minutes per year** (four hours and 40 minutes).

</div>

<div v-click>

  - The upper limit on availability is **"Three Nines" (99.9%)**
</div>

<div v-click>

- Add expected operational offline for routine maintenance and updates:
  - four hours per operation, six times per year = **24 hours per year**. => 1440 minutes + 280 minutes = 1720 minutes
    - `minutes_in_year = 60 minutes/hour * 24 hours/day * 365 days/year = 525,600`
    - Availability = ((525,600 - 1720) / 525,600) * 100 = 99.6726%
- In total, the availability is approximately **"Two Nines" (99%)**

</div>

---

# Recovery Time Objective (RTO) and
# Recovery Point Objective (RPO)

- A good resiliency strategy should also include Disaster Recovery (DR) objectives based on strategies to recover your workload in case of a disaster event.
- **Recovery Time Objective (RTO)**: How long does it take you to recover and bring the system back online after a failure? 
  - It's measured in seconds
- **Recovery Point Objective (RPO)**: How much data is lost if the system fails? 
  - It's measured in data units (e.g., 10 GB) or time (e.g., 1 hour worth of data).

---
layout: center
---

# Cloud Storage



--- 

# Introduction

- Prior to delving into cloud storage discussions, it's crucial to understand the nature of our data, storage volume types (SSD vs HDD), and IOPS (Input/Output Operations Per Second).
- This will aid us in selecting the most suitable storage solution.

---
layout: center
---

# Data Types
- **Structured data**: Data that is organized and follows a specific format, such as tables in SQL databases or collections in NoSQL databases. (e.g., customer name, address, purchase history)
- **Semi-structured data**: Flexible format, often with tags (Ex: JSON, YAML, XML, log files)
- **Unstructured data**: No predefined format (Ex: text files, images, videos, audio, social media posts, web pages, emails)

---
layout: center
---


# HDD (Hard Disk Drive)
- HDDs are traditional spinning disks and are generally cheaper than SSDs.
- They are good for applications with large amounts of data that need to be stored cost-effectively and are accessed less frequently.
- HDDs typically have lower IOPS (Input/Output Operations Per Second) compared to SSDs, so they may not be the best choice for high-performance applications.
- HDD volumes are ideals for sequential large block throughput-intensive workloads that are bound by throughput (e.g., big data, data warehouse, and log processing)


---
layout: center
---

# SSD (Solid State Drive)
- SSDs are faster and more reliable than HDDs, but they are also more expensive.
- They provide high IOPS and are a good choice for high-performance applications that require fast access to data, such as databases and real-time processing systems.
- SSDs are also a good choice for applications that require high input/output operations per second (IOPS), such as transactional or write-intensive applications (e.g., transactional applications, databases, and boot volumes)
- For an instance storage volume (the VM OS boot disk), SSDs (Solid State Drives) are generally considered the more appropriate choice.

---
layout: center
---

# IOPS (Input/Output Operations Per Second)

- IOPS are a unit of measure representing input/output operations per second.
- The operations are measured in `KiB`
- Each operation is a read/write to/from a disk volume
- Each operation can vary in the amount of data being read/written.
- IOPS used to benchmark computer storage devices like hard disk drives (HDD), solid state drives (SSD), and storage area networks (SAN).
- I/O size is capped at 256 KiB for SSD volumes and 1,024 KiB for HDD volumes because SSD volumes handle small or random I/O much more efficiently than HDD volumes.
  - For example, if an I/O operation for an SSD volume is more than 256 KiB, the operation is split into multiple operations.
- Higher IOPS can often mean improved performance for certain applications, but the actual impact can vary depending on how the storage is used.
- Applications with high IOPS requirements would benefit from SSDs due to their fast read/write speeds.

---

# Cloud Storage Solutions

- Instance storage volumes (OS Disks)
- Block-level storage volumes
- Shared File storage
- Object/Blob storage
- Queue Storage
- Table Storage
- Archive storage
- Cached storage

---

# Instance storage volumes (OS Disks)

- Ephemeral block storage for VM instances.
- Data is persistent during orderly instance reboots but will be lost if the VM instance is terminated or failed.
- Located on the hardware itself that is running your VM instance. This results in a high performance.
- Availability and durability numbers are often not reported.
- Although it’s not recommended as a storage for any application, it can used as a temporary high-performance storage for applications' buffers, queues, and caches.
- Using Instance Storage Volumes:
 - Create an VM instance, select the OS disk, select the type HDD or SSD and class.
 
---

# Block storage (I)

- A network-attached block storage volumes for VM instances.
- Block storage volumes can be attached to a single instance in a particular region, while multiple volumes can be attached to a single instance.
- Ideal for workloads that require the lowest-latency access to data from a - single instance.
- Block storage volumes are available in SSD or HDD options.
- Volumes are often replicated across multiple servers in a single Availability - Zone to prevent data loss.
- To maximize durability and availability, you should create snapshots of your - block volumes frequently and move it to a region scope.
- Examples: AWS EBS volumes, Azure managed disks, and GCP Persistent Disk.


---

# Block storage (II)
- The number of expected failures for block storage volumes refers to the estimated number of times a storage volume might fail over a given period of time.
- This is typically expressed as a percentage or a rate over time.
- Cloud providers often use redundancy and replication to minimize the risk of data loss due to volume failures.
- For example, Amazon's Elastic Block Store (EBS) volumes are designed to deliver a very low annual failure rate (AFR) between 0.1% - 0.2%.
  - **Number of expected failures** = **AFR% x Total number of volumes**
  - For example, if you have 10,000 volumes, only 0.1 volumes are expected to fail each year.
- The exact number can vary depending on the specific cloud provider, the type of storage volume (e.g., SSD vs HDD), and the specific configuration of the storage service.


---

# Block storage (III)

<div></div>

![](/images/Block-Storage-Volume.png)

---

# Resilience Storage

- Can we further increase durability?

<div v-click>

  - Custom solutions to copy snapshots to other regions.
- Is the current solution resilient if stored in the same account on the same cloud provider?

</div>

<div v-click>

  - What if your account is comprised.
</div>

<div v-click>

- Resilient storage architecture implies not only accounting for hardware failure and human errors but also malicious activities.
</div>


---

# Shared File Storage (I)

- A scalable network file system storage compute resources (e.g., VM instances, containers, and FaaS/serverless).
  - Scope is often region-based.
- Can be mounted by multiple instances or services across multiple regions with concurrent read and write access.
- Volumes provide a resilient shared storage with an availability of three nines (99.9%) and durability of eleven nines (99.999999999%).
- It's often used in multi-client access applications that concurrently access data from multiple VM instances.

---
layout: full
---
# Shared File Storage (II)

<div></div>

![](/images/Shared-File-Storage.png)

---

# Object Storage (I)

- A scalable and durable object storage service that makes data available through an API.
- Items are stored inside buckets using a unique bucket name in a given region.
- Region scoped and objects are replicated across all Availability Zones (AZs) within a single region but not across all regions.
- Usage patterns: static content and media objects, static websites, Single Page Applications (SPAs), data-store for computation and large-scale analytics, highly durable backups of critical data.
- It's not designed for storing rapidly changing data or meta data about the stored object. 

---

# Object Storage (II)

- Often provided at different storage classes:
  - **Standard class**: objects are deployed at a region scope with four nines of availability and 11 nines of durability.
    - Data is being replicated across at least three availability zones
    - individual copies of data are validated on a regular schedule (checksum testing)
  - **Infrequent access class**: Availability drops to three nines
  - **Intelligent tearing class**: It’s workload that migrates your objects back and fourth between object storage classes.
  - **One-zone infrequent access class**: Availability drops to 99.5%
 
---

# Archive Storage

- Low-cost highly durable storage services for data archiving and online backups with a long recovery/retrieval time.
- It's a cost-effective storage for data that requires encrypted archival storage with infrequent read access with a long recovery time objective (RTO).
- Data stored in archives are not available immediately. Retrieval jobs typically require a few hours to complete.
- Data can be transferred seamlessly between object storage services and archive storage using custom data lifecycle policies.

---
layout: center
---

# Storage Options and Scenarios

---

# Question 1

<div></div>

Your team has been asked to implement a storage infrastructure that can support multiple AZs within a region. Multiple VM instances will require access to the data. High availability is more important than performance. Which of the following solutions meet the requirements with the least operational overhead?

  1. Archive storage gateway in volume cache mode. Data stored in Object-Storage.
  2. Individual block storage volumes attached to VM instances. Data downloaded from object-storage.
  3. Deploy a shared File System installed on all instances  with multiple partitions and replicas of data.
  4. Shared File Storage volume deployed in a region. Each instance mounts the volume via NFS.


---

# Question 2

<div></div>

An application is running on a single VM instance with no opportunity for horizontal scaling. The application data is stored and accessed from a single Block Storage volume. You've been asked to maximize the durability of this data with the ability to recover from accidental deletion of single files. Which of the following steps can be implemented to best meet the requirements? (Choose two)

1. Migrate the data to an instance storage to improve IOPS performance.
2. Create a second block storage volume and write all data to both volumes.
3. Using an archival service, schedule daily snapshots of the data.
4. Create a single image of the instance.
5. Migrate the data into a block storage raid filesystem.




---

# Question 3

<div></div>

A company plans to migrate all of their applications to the cloud and are considering block storage volumes. They are worried that volumes may not be appropriate for the existing workloads due to compliance requirements, downtime scenarios, and IOPS performance. 
Which of the following is true when choosing Block Storage Volumes for migration. [Choose two]

1. Block Storage Volumes are off-instance storage devices that can persist independently from the life of an instance.
2. Block Storage Volumes are often replicated across multiple regions.
3. Backups/Snapshots can be taken of Block Storage Volumes and stored in a region-scope (e.g., Object Storage).
4. Block Storage Volumes can be attached to any VM instance in any Availability Zone.
5. Block Storage Volumes can not be configured live in production and (e.g., changing their volume type, volume size, and IOPS capacity) without service interruptions.




---

# Question 4

<div></div>

A company is building an internal application that processes financial data for their clients. They require a storage service that can handle future increases in storage capacity of up to 16 TB and can provide the lowest-latency access to their data. The web application will be hosted in a single VM instance that will process and store data to the storage service.
Which of the following storage services would you recommend?

1. Block Storage
2. Object Storage
3. Storage Gateway
4. Shared File Storage


---

# Question 5

<div></div>

A content management system (CMS) is hosted on a fleet of VM instances. Currently, the system stores the file documents that the users upload in a POSIX-compliant file system. They noticed that the system performance is quite slow and are looking to improve the architecture of the system. 
What options will be more suitable to improve the performance of their system?
1. Block Storage
2. Object Storage
3. Cached-Storage Service
4. Shared File Storage



---

# References
- [AWS "AWS Well-Architected". Retrieved 05 January 2024](https://docs.aws.amazon.com/wellarchitected/)
- [Fowler, Martin (10 September 2018). "Serverless Architectures". Retrieved 26 January 2018.](https://martinfowler.com/articles/serverless.html)
