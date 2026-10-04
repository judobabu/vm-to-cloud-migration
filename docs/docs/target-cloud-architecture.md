# AWS & Azure Target Cloud Architecture

## Overview

The target architecture provides a controlled landing environment for workloads migrated from the existing VMware datacenter.

AWS and Azure follow the same core architectural principles while using their respective native services.

## High-Level Architecture

```text id="f2zq8k"
              ON-PREMISES VMware
                     |
                     | Hybrid Connectivity
                     |
          +----------+----------+
          |                     |
          v                     v
     AWS Landing Zone      Azure Landing Zone
          |                     |
          v                     v
       Network               Network
          |                     |
          v                     v
     Compute / VM           Compute / VM
          |                     |
          v                     v
   Storage / Database    Storage / Database
          |                     |
          +----------+----------+
                     |
                     v
              Security & Operations
```

## AWS Target

The AWS environment would typically include:

* AWS Organizations / account structure
* VPC-based network architecture
* EC2 for migrated VM workloads
* EBS and other storage services
* Managed database services where appropriate
* IAM for access control
* Cloud monitoring and logging
* Backup and recovery services
* Hybrid connectivity to the datacenter

## Azure Target

The Azure environment would typically include:

* Management groups and subscriptions
* Azure Virtual Network
* Azure Virtual Machines
* Azure storage services
* Managed database services where appropriate
* Microsoft Entra ID for identity
* Azure monitoring and logging
* Backup and recovery services
* Hybrid connectivity to the datacenter

## Landing Zone Principles

Before production workloads are migrated, the cloud environment should establish common foundations for:

* Network connectivity
* Identity and access
* Security controls
* Logging and monitoring
* Resource organization
* Backup
* Governance
* Cost management

## Hybrid Connectivity

During migration, on-premises and cloud environments will normally coexist.

Connectivity should support:

* Application communication
* DNS resolution
* Identity services
* Management access
* Data transfer
* Monitoring
* Migration activities

The connectivity design should account for security, latency, bandwidth, availability, and routing.

## Workload Placement

Workload placement is determined by application requirements.

```text id="h8h0yk"
                 Workload
                    |
          +---------+---------+
          |         |         |
          v         v         v
         AWS      Azure    On-Prem
          |         |         |
      Requirement-based Placement
```

The architecture does not assume that every workload must move to the same cloud.

## Architecture Principle

**Landing zones and shared services should be established before migrating business-critical workloads.**

This provides a consistent foundation for security, networking, operations, and governance.

## Outcome

The target architecture provides:

* Standard cloud foundations
* Controlled workload placement
* Hybrid connectivity
* Consistent security and operations
* A scalable platform for future migration waves
