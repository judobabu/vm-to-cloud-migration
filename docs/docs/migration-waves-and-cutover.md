# Migration Waves & Cutover

## Overview

Large-scale VM migration should be performed in controlled waves rather than moving all workloads at once.

Workloads are grouped based on dependencies, business criticality, technical complexity, and migration readiness.

## High-Level Wave Model

```text
Assessment
    |
    v
Pilot / Low-Risk Workloads
    |
    v
Standard Business Workloads
    |
    v
Complex / Highly Dependent Workloads
    |
    v
Business-Critical Workloads
```

## Wave Planning

Each migration wave should consider:

* Application dependencies
* Business owner approval
* Technical readiness
* Network and security requirements
* Migration effort
* Application downtime
* Validation requirements
* Rollback requirements

## Example Wave Structure

| Wave | Workload Type         | Approach                            |
| ---- | --------------------- | ----------------------------------- |
| 1    | Low-risk workloads    | Validate migration process          |
| 2    | Standard applications | Repeat proven process               |
| 3    | Complex applications  | Detailed dependency planning        |
| 4    | Critical applications | Controlled migration and validation |

The actual number and composition of waves would depend on the environment.

## Migration Flow

```text
Plan
  |
  v
Prepare Target Environment
  |
  v
Migrate
  |
  v
Validate
  |
  v
Business Approval
  |
  v
Cutover
  |
  v
Operate
```

## Cutover Planning

Before production cutover, the team should confirm:

* Application readiness
* Network connectivity
* DNS requirements
* Security rules
* Data synchronization
* Backup availability
* Monitoring
* Support coverage
* Business validation
* Rollback plan

## Validation

Post-migration validation should cover:

* VM availability
* Application connectivity
* Database connectivity
* Network communication
* Authentication
* Application functionality
* Monitoring
* Backup
* Performance

Business owners should confirm that the application is functioning as expected before the migration is considered complete.

## Rollback

A rollback decision should be defined before cutover.

```text
                 Cutover
                    |
                    v
              Validation
               /       \
            PASS       FAIL
             |           |
             v           v
          Operate     Rollback
```

Rollback criteria should be agreed in advance based on business impact, application health, data consistency, and technical validation.

## Architecture Principle

**Every migration wave should have a clear entry criteria, validation process, success criteria, and rollback approach.**

This makes the migration repeatable and reduces risk as the number of migrated workloads increases.
