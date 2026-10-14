# Cloud Computing

## Concepts to learn

- **Cloud computing:** On-demand access to configurable computing resources over a network, usually with rapid provisioning and measured usage.
- **IaaS:** Provider supplies virtualized compute, storage, and networking; customer manages more of the operating system and applications.
- **PaaS:** Provider manages the platform/runtime; customer focuses mainly on deploying and managing applications and data.
- **SaaS:** Provider delivers a complete application; customer uses it without managing its underlying platform.
- **Public, private, hybrid:** Public cloud is provider-operated and shared across customers; private cloud is dedicated to one organization; hybrid combines environments with integration between them.
- **Scalability and elasticity:** Scalability is the ability to handle growth by adding/removing capacity; elasticity emphasizes adapting capacity to changing demand.
- **Virtualization:** A hypervisor enables multiple virtual machines to share physical hardware. Containers isolate applications while sharing the host OS kernel.
- **Availability and resilience:** Redundancy and fault-tolerant design help services continue through component failures; backups help restore data but are not a complete availability strategy.
- **Shared responsibility:** Provider/customer security duties vary by service model. Customers remain responsible for appropriate data use, identities, and configuration.
- **Serverless:** The provider manages server provisioning and scaling; the customer deploys functions/services and pays according to a provider's usage model.

## Original practice MCQs

### Questions

1. Which cloud service model typically gives customers virtual machines, networks, and storage while they manage the guest OS?
   A) SaaS  B) PaaS  C) IaaS  D) Desktop publishing

2. A user accesses a provider-hosted email application through a browser. This is most commonly:
   A) IaaS  B) PaaS  C) SaaS  D) Bare metal

3. What is elasticity?
   A) Automatically or rapidly adjusting resources with demand
   B) Compressing every file
   C) Removing all network access
   D) A type of database key

4. Which best describes a hybrid cloud?
   A) Only one laptop with no network
   B) A combination of private and public cloud environments
   C) A single spreadsheet shared by a team
   D) Two CPUs in one server

5. What does a hypervisor primarily do?
   A) Manages virtual machines on physical hardware
   B) Resolves domain names
   C) Creates SQL queries
   D) Replaces user authentication

6. Which statement about containers is generally true?
   A) Each container must run a complete separate physical machine.
   B) Containers commonly share the host OS kernel while isolating processes.
   C) Containers are only used for spreadsheets.
   D) Containers eliminate the need for security.

7. In a shared-responsibility model, which remains important for the customer even when using managed cloud services?
   A) Correctly configuring identities and access
   B) Manufacturing the provider's servers
   C) Maintaining the provider's building power supply
   D) Writing the provider's hypervisor

8. A service launches code in response to events without the customer provisioning servers. This is commonly called:
   A) Serverless computing  B) Dial-up networking  C) Local-only computing  D) Manual scaling

### Answer key and explanations

1. **C — IaaS.** The customer has substantial OS and application control.
2. **C — SaaS.** The user consumes the complete provider-hosted application.
3. **A.** Elasticity means capacity can track changing demand.
4. **B.** Hybrid combines private and public cloud environments, typically with some integration.
5. **A.** A hypervisor creates and manages virtual machines.
6. **B.** Containers isolate application processes while generally sharing the host kernel.
7. **A.** Cloud use does not remove customer responsibility for identities, permissions, data, or secure configuration.
8. **A.** Serverless abstracts server provisioning from the application developer.
