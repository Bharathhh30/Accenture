# DevOps

**Assessment priority: Role-dependent** — important for cloud/software delivery roles, but not established as a universal general campus MCQ section by the public sources reviewed.

| Concept | One-line last-minute reminder |
|---|---|
| DevOps | DevOps combines development and operations practices to deliver software reliably through collaboration and automation. |
| Continuous Integration (CI) | CI frequently merges code and runs automated build/tests to find integration problems early. |
| Continuous Delivery | Continuous Delivery keeps changes deployable and release-ready, with production release typically gated/approved. |
| Continuous Deployment | Continuous Deployment automatically releases passing changes to production without a manual release approval step. |
| Pipeline | A CI/CD pipeline automates stages such as checkout, build, test, scan, package, and deploy. |
| Version control | Version control tracks changes, supports collaboration, and enables branching, merging, and rollback. |
| Build artifact | A build artifact is a versioned output package/image produced from source and promoted through environments. |
| Automated testing | Unit, integration, system, and acceptance tests provide feedback at different scopes. |
| Infrastructure as Code | IaC defines infrastructure declaratively or programmatically so it can be reviewed and reproduced. |
| Configuration management | Configuration management keeps system/app settings consistent across machines and environments. |
| Container | A container packages an application and dependencies while sharing the host OS kernel. |
| Virtual machine | A virtual machine runs a guest OS on virtualized hardware managed by a hypervisor. |
| Container orchestration | Orchestration schedules containers and manages scaling, service discovery, health checks, and rollouts. |
| Immutable infrastructure | Immutable infrastructure is replaced with a new version rather than modified in place. |
| Blue-green deployment | Blue-green maintains two environments and switches traffic to the newly deployed one after validation. |
| Canary deployment | Canary deployment releases to a small user/traffic subset first and expands if health remains acceptable. |
| Rollback | A rollback returns a release/configuration to a known-good version when a deployment causes problems. |
| Monitoring | Monitoring tracks system health and performance through metrics, logs, traces, and alerts. |
| Logs / metrics / traces | Logs record events, metrics measure numeric signals over time, and traces follow requests across services. |
| SLI / SLO / SLA | SLI is a measured indicator, SLO is an internal target, and SLA is a formal service commitment. |
| Reliability and error budget | An error budget is the tolerable unreliability implied by an SLO and guides release-risk decisions. |
| DevSecOps | DevSecOps integrates security checks and secure practices throughout the delivery lifecycle. |
| Secrets management | Store credentials/keys in controlled secret-management systems; do not commit secrets to source code. |
| Observability | Observability uses outputs such as logs, metrics, and traces to infer internal system state. |
