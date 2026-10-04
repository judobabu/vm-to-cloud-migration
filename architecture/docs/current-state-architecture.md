# Current-State Datacenter Architecture

## Overview

The current-state environment represents a typical enterprise on-premises datacenter hosting business applications on VMware infrastructure.

The architecture provides the baseline for discovery, dependency analysis, workload classification, and migration planning toward AWS and Azure.

## Current-State Architecture

```text
                    ENTERPRISE USERS
                           |
                           v
                  +-------------------+
                  | Enterprise Network|
                  +-------------------+
                           |
                           v
              +-------------------------+
              | On-Prem Datacenter      |
              |                         |
              | VMware / ESXi Clusters  |
              |        |                |
              |        v                |
              |   Virtual Machines      |
              |        |                |
              |   +----+----+           |
              |   |         |           |
              |  Apps     Databases      |
              |   |         |            |
              |   +----+----+            |
              |        |                 |
              |   Shared Storage         |
              |        |                 |
              |   Backup / DR            |
              +-------------------------+
                           |
                           v
                 Enterprise Services
```

## Major Components

### VMware Infrastructure

* VMware ESXi hosts
* VMware clusters
* Virtual machines
* Virtual networking
* Shared storage
* High-availability capabilities
* Virtual machine lifecycle management

### Application Workloads

The environment may contain multiple workload categories:

* Web applications
* Application servers
* Database servers
* Middleware platforms
* File and utility servers
* Development and test environments
* Production workloads

### Enterprise Dependencies

VM workloads commonly depend on shared enterprise services such as:

* DNS
* DHCP
* Active Directory / identity services
* Authentication services
* Network services
* Monitoring
* Backup
* Security tooling
* Configuration management
* Enterprise storage

## Current-State Assessment Areas

Before migration, each workload should be evaluated across several dimensions:

| Assessment Area   | Key Considerations                                         |
| ----------------- | ---------------------------------------------------------- |
| Compute           | CPU, memory, utilization, sizing                           |
| Storage           | Capacity, performance, IOPS, growth                        |
| Network           | Connectivity, bandwidth, latency                           |
| Application       | Architecture and business criticality                      |
| Dependencies      | Application-to-application and infrastructure dependencies |
| Operating System  | OS version, support status, compatibility                  |
| Database          | Engine, version, HA/DR requirements                        |
| Security          | Security controls and compliance requirements              |
| Availability      | SLA, HA and recovery requirements                          |
| Backup            | Backup frequency and retention                             |
| Disaster Recovery | RPO/RTO and recovery architecture                          |
| Business          | Criticality, owner and migration priority                  |

## Architectural Objective

The current-state architecture establishes the baseline required to determine:

1. Which workloads should move to AWS or Azure.
2. Which workloads should remain on-premises.
3. Which workloads require modernization.
4. Which dependencies must be migrated together.
5. Which connectivity and security controls are required.
6. How workloads should be grouped into migration waves.

The assessment output becomes the foundation for the target cloud architecture and migration factory.
