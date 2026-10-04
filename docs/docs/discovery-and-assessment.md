# VM Discovery & Assessment

## Overview

VM discovery and assessment establishes a reliable inventory of workloads running in the existing VMware environment.

The assessment combines infrastructure characteristics, application information, utilization, dependencies, operational requirements, and business criticality to determine the appropriate migration approach and target platform.

## Discovery Sources

Potential discovery sources include:

* VMware vCenter
* ESXi infrastructure
* CMDB
* Application inventory
* Storage platforms
* Network and DNS services
* Monitoring platforms
* Backup platforms
* Application owner information
* Existing architecture documentation

## VM Discovery Data

Typical VM inventory attributes include:

| Category             | Example Information             |
| -------------------- | ------------------------------- |
| VM Identity          | VM name, identifier             |
| Application          | Application name and component  |
| Environment          | DEV, TST, STG, PRD              |
| Operating System     | Linux / Windows and version     |
| Compute              | vCPU, memory                    |
| Storage              | Allocated capacity, utilization |
| Network              | IP, subnet, network zone        |
| VMware               | Cluster, host, datastore        |
| Availability         | HA requirements                 |
| Backup               | Backup policy and retention     |
| DR                   | RPO / RTO requirements          |
| Ownership            | Application and support owner   |
| Business Criticality | Critical / High / Medium / Low  |

## Utilization Assessment

Historical utilization should be considered rather than relying only on allocated VM resources.

Key metrics include:

* CPU utilization
* Memory utilization
* Storage consumption
* Storage growth
* Network throughput
* Peak utilization
* Seasonal or business-cycle patterns

This helps identify oversized or undersized workloads before cloud sizing.

## Application Assessment

Each VM should be evaluated in the context of the application it supports.

Assessment areas include:

* Application architecture
* Application tier
* Database dependencies
* External integrations
* Authentication dependencies
* Shared services
* Licensing requirements
* Performance requirements
* Availability requirements
* Business criticality

## Dependency Assessment

Infrastructure discovery should be supplemented with application dependency mapping.

Examples include:

```text
Web Server
    |
    +---- Application Server
              |
              +---- Database
              |
              +---- Active Directory
              |
              +---- External Services
              |
              +---- Shared Storage
```

Dependency information is important for determining which workloads need to migrate together within the same migration wave.

## Migration Readiness Classification

Workloads can be classified using a high-level readiness model:

| Classification          | Description                                              |
| ----------------------- | -------------------------------------------------------- |
| Ready                   | Limited dependencies and clear target architecture       |
| Requires Planning       | Additional dependency or security analysis required      |
| Requires Remediation    | OS, application, licensing, or infrastructure issues     |
| Modernization Candidate | Opportunity to move toward managed/cloud-native services |
| Retain                  | Business or technical reasons to remain on-premises      |
| Retire                  | Workload no longer required                              |

## Assessment Output

The assessment produces a workload profile that can be used by the migration planning team.

Example:

```text
VM
 |
 +-- Application
 +-- Owner
 +-- Environment
 +-- OS
 +-- Compute Profile
 +-- Storage Profile
 +-- Network Profile
 +-- Dependencies
 +-- Business Criticality
 +-- Availability / DR
 +-- Migration Readiness
 +-- Recommended Migration Strategy
 +-- Target Cloud
```

## Architectural Objective

The objective is to establish a consistent, evidence-based view of the existing environment before migration decisions are made.

Discovery and assessment should answer:

1. What workloads exist?
2. What does each workload depend on?
3. How is each workload currently sized and utilized?
4. How business-critical is the workload?
5. Is the workload technically ready for migration?
6. Which migration strategy is appropriate?
7. Should the workload target AWS, Azure, remain on-premises, or be retired?

The resulting workload inventory becomes a key input to dependency mapping, migration strategy, wave planning, and target cloud architecture.
