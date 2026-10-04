# Workload Classification & Migration Readiness

## Overview

Workload classification converts discovery and dependency information into actionable migration decisions.

Each workload is evaluated based on technical characteristics, application dependencies, business criticality, operational requirements, and modernization opportunities.

The outcome is a recommended migration strategy and target platform.

## Classification Dimensions

Workloads should be evaluated across multiple dimensions:

| Dimension               | Considerations                       |
| ----------------------- | ------------------------------------ |
| Business Criticality    | Critical, High, Medium, Low          |
| Technical Complexity    | Simple, Moderate, Complex            |
| Dependencies            | Low, Medium, High                    |
| Availability            | HA / SLA requirements                |
| Performance             | CPU, memory, storage, network        |
| Security                | Compliance and security requirements |
| Operating System        | Supported / unsupported              |
| Application Lifecycle   | Strategic / Legacy / End-of-Life     |
| Cloud Suitability       | AWS / Azure / Hybrid / On-Prem       |
| Modernization Potential | Low / Medium / High                  |

## Migration Readiness

A high-level readiness model can be used:

```text
                    Workload
                       |
             +---------+---------+
             |                   |
        Technically Ready    Requires Action
             |                   |
             v                   v
       Migration Planning   Remediation
             |                   |
             +---------+---------+
                       |
                       v
                Migration Wave
```

## Workload Classification Matrix

| Classification         | Characteristics                   | Typical Action                    |
| ---------------------- | --------------------------------- | --------------------------------- |
| Low Complexity         | Few dependencies, standard OS     | Prioritize for early migration    |
| Moderate Complexity    | Multiple application dependencies | Detailed wave planning            |
| High Complexity        | Many dependencies or strict SLA   | Detailed architecture and testing |
| Legacy                 | Aging OS/application stack        | Remediate or modernize            |
| Cloud-Native Candidate | Suitable for managed services     | Evaluate modernization            |
| Retain                 | Business/technical constraints    | Keep on-premises temporarily      |
| Retire                 | No longer required                | Decommission                      |

## Migration Strategy Alignment

Classification should feed the migration strategy decision.

```text
Workload Assessment
        |
        v
+----------------------+
| Business & Technical |
| Classification       |
+----------------------+
        |
        v
+----------------------+
| Migration Strategy   |
+----------------------+
   |    |    |    |
   v    v    v    v
 Rehost Replatform
 Refactor Retain
   |
   +---- Retire / Repurchase / Relocate
```

The final strategy should be determined by business requirements, application characteristics, technical constraints, cost, risk, and long-term platform direction.

## Target Cloud Selection

AWS versus Azure should not be selected solely based on VM compatibility.

Evaluation factors may include:

* Existing enterprise cloud strategy
* Identity platform
* Network architecture
* Application dependencies
* Existing cloud services
* Data residency requirements
* Security and compliance requirements
* Operational capabilities
* Licensing considerations
* Cost and capacity
* Availability and disaster recovery requirements

## Example Assessment

| Workload             | Complexity | Dependencies | Readiness    | Strategy   | Target |
| -------------------- | ---------- | ------------ | ------------ | ---------- | ------ |
| Web Application      | Low        | Low          | Ready        | Rehost     | AWS    |
| Business Application | Medium     | Medium       | Ready        | Replatform | Azure  |
| Legacy Application   | High       | High         | Remediation  | Refactor   | Azure  |
| Internal Utility     | Low        | Low          | Ready        | Rehost     | AWS    |
| Retired Application  | N/A        | N/A          | Not Required | Retire     | N/A    |

The examples are illustrative and do not represent a specific production environment.

## Migration Priority

A workload's migration priority can consider:

* Business value
* Technical readiness
* Dependency complexity
* Risk
* Cloud suitability
* Application lifecycle
* Operational impact
* Migration effort

A low-complexity workload with limited dependencies may be a good candidate for an early migration wave, while highly interconnected business-critical workloads generally require additional assessment and testing.

## Architectural Objective

The classification process creates a consistent decision framework between discovery and migration execution.

The final assessment should provide:

1. Workload classification.
2. Migration readiness.
3. Recommended migration strategy.
4. Target cloud recommendation.
5. Dependency considerations.
6. Migration priority.
7. Required remediation.
8. Initial migration-wave recommendation.

This creates a traceable path from **VM discovery → application assessment → migration decision → wave planning**.
