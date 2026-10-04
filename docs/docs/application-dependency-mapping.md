# Application Dependency Mapping

## Overview

Application dependency mapping identifies the relationships between virtual machines, application components, databases, infrastructure services, and external systems.

Understanding these dependencies is critical for determining migration waves, sequencing workloads, designing cloud connectivity, and minimizing application disruption.

## Dependency Model

A typical enterprise application may contain multiple interconnected components:

```text
                    USERS
                      |
                      v
                Load Balancer
                      |
                      v
                 Web Tier
                      |
                      v
              Application Tier
                 /        \
                /          \
               v            v
          Database       Middleware
               |              |
               v              v
          Storage        External APIs
               |
               v
          Backup / DR
```

## Dependency Categories

### Application Dependencies

* Web-to-application communication
* Application-to-database communication
* Application-to-application interfaces
* Middleware dependencies
* Batch processing dependencies
* External API integrations

### Infrastructure Dependencies

* DNS
* DHCP
* Active Directory / identity
* NTP
* Load balancing
* Network services
* Shared storage
* Backup infrastructure
* Monitoring platforms

### Security Dependencies

* Authentication
* Authorization
* Security agents
* Vulnerability management
* Firewall policies
* Certificate services
* Secrets management

## Dependency Mapping Inputs

Dependency information may be derived from multiple sources:

| Source                 | Purpose                                      |
| ---------------------- | -------------------------------------------- |
| CMDB                   | Application and infrastructure relationships |
| VMware Inventory       | VM and infrastructure relationships          |
| Network Data           | Communication paths                          |
| Monitoring             | Runtime communication patterns               |
| Application Owners     | Business and functional dependencies         |
| Architecture Documents | Known application relationships              |
| Firewall Rules         | Required network flows                       |
| DNS Records            | Service and hostname relationships           |

## Dependency Classification

Dependencies can be categorized to simplify migration planning:

| Type           | Example                                    |
| -------------- | ------------------------------------------ |
| Critical       | Database required by application           |
| Shared         | Enterprise DNS or identity service         |
| External       | Third-party API                            |
| Infrastructure | Monitoring or backup                       |
| Optional       | Non-critical integration                   |
| Unknown        | Dependency requiring further investigation |

Unknown dependencies should be resolved before production cutover wherever practical.

## Migration Wave Considerations

Dependency mapping directly influences migration grouping.

For example:

```text
Wave 1
  |
  +-- Application A
  |     |
  |     +-- Web VM
  |     +-- App VM
  |     +-- Database VM
  |
  +-- Required Middleware
  |
  +-- Required Network / Security Rules
```

Highly dependent workloads should generally be migrated in a coordinated sequence or within the same migration wave.

Shared services may require a different strategy because they can support workloads across multiple waves.

## Dependency Validation

Before migration, identified dependencies should be validated against:

* Application owner knowledge
* Network communication data
* Firewall requirements
* DNS records
* Authentication requirements
* Database connections
* External integrations
* Monitoring and backup requirements

This reduces the risk of discovering critical dependencies during cutover.

## Architectural Objective

Dependency mapping transforms the VM inventory into an application-aware migration model.

The resulting dependency information becomes an input to:

1. Migration strategy selection.
2. Workload grouping.
3. Migration wave planning.
4. Network and security design.
5. Cutover sequencing.
6. Validation planning.
7. Rollback planning.

The goal is not simply to move VMs to the cloud, but to migrate **complete application capabilities with their required dependencies and operational controls**.
