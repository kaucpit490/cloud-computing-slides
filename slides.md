---
# try also 'default' to start simple
theme: default
presenter: true
title: 'Cloud Computing | Compute and Storage'
titleTemplate: '%s - CPIT-405'
# apply any windi css classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: | 
    Cloud Computing | Compute and Storage
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
  timeout: 30000
  dark: false
  withClicks: false
  withToc: false
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
layout: Center
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


