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

