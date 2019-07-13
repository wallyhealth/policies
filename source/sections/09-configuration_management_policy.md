# 9. Configuration Management Policy

Wally standardizes and automates configuration management through the use of Chef/Salt scripts as well as documentation of all changes to production systems and networks. Chef and Salt automatically configure all Wally systems according to established and tested policies, and are used as part of our Disaster Recovery plan and process.

## 9.1 Applicable Standards

### 9.1.1 Applicable Standards from the HITRUST Common Security Framework

* 06 - Configuration Management

### 9.1.2 Applicable Standards from the HIPAA Security Rule

* 164.310(a)(2)(iii) Access Control & Validation Procedures

## 9.2 Configuration Management Policies

1. Infrastructure as Code (IaC) recipes are used to standardize and automate configuration management.
2. No systems are deployed into Wally environments without approval of the Wally CTO.
3. All changes to production systems, network devices, and firewalls are approved by the Wally CTO before they are implemented to assure they comply with business and security requirements.
4. All changes to production systems are tested before they are implemented in production.
5. Implementation of approved changes are only performed by authorized personnel.
6. Tooling to generate an up-to-date inventory of systems, including corresponding architecture diagrams for related products and services, is hosted on GitHub.
7. All frontend functionality is separated from backend systems by being deployed on separate servers or containers.
8. All software and systems are tested using unit and integration tests, when possible.
9. All committed code is reviewed using pull requests to assure software code quality and proactively detect potential security issues in development.
10. Wally utilizes staging environments that mirror production to assure proper function.
11. All formal change requests require unique ID and authentication.
12. Clocks are continuously synchronized to an authoritative source across all systems using NTP or a platform-specific equivalent. Modifying time data on systems is restricted.

## 9.3 Provisioning Production Systems

1. Before provisioning any systems, a request must be filed in the QMS.
   * QMS access requires authenticated users.
   * The CTO grants access to the QMS following the procedures covered in the [Access Establishment and Modification section](#7.2-access-establishment-and-modification).
2. The CTO, or an authorized delegate of the CTO, must approve the provisioning request before any new system can be provisioned.
3. Once provisioning has been approved, the ops team member must configure the new system according to the standard baseline chosen for the system's role.
4. For systems that use block storage, an encrypted block data volume needs to be added.
5. Once the system has been provisioned, it needs to be verified that the secure baseline has been applied to the new system, including (but not limited to) verifying the following items:
   * Removal of default users used during provisioning.
   * Network configuration for system.
   * Data volume encryption settings.
   * Intrusion detection and virus scanning software installed.
   * All items listed below in the operating system-specific subsections below.
6. Vulnerability scanning needs to be enabled for the new system once it has been correctly configured.
7. The new system may be rotated into production once the CTO verifies all the provisioning steps listed above have been correctly followed and has marked the request with the `Approved` state.

### 9.3.1 Provisioning Linux Systems

1. Linux systems have their baseline security configuration applied via hardened images which cover:
   * Ensuring that the machine is up-to-date with security patches and is configured to apply patches in accordance with our policies.
   * Stopping and disabling any unnecessary OS services.
   * Installing and configuring a host-based intrusion detection system.
   * Configuring 15-minute session inactivity timeouts.
   * Installing and configuring a virus scanner.
   * Installing and configuring the NTP daemon, including ensuring that modifying system time cannot be performed by unprivileged users.
   * Configuring audit logging as described in the [Auditing Policy section](#8.-auditing-policy).
2. Any additional activities must be clearly documented in the request by specifying the purpose of the new system.

### 9.3.2 Provisioning Management Systems

1. Provisioning management systems such as VPN appliances follows the same procedure as provisioning a production system.
2. Critical infrastructure services such as auditing, logging and monitoring must be appropriately configured in accordance with all Wally policies.
3. Critical infrastruture roles applied to new systems must be clearly documented in the request.

## 9.4 Changing Existing Systems

1. Subsequent changes to already-provisioned systems are unconditionally handled by one of the following methods:
   * Changes to IaC recipes.
   * For configuration changes that cannot be handled by IaC recipes, a runbook describing exactly what changes will be made and by whom.
2. Configuration changes to IaC recipes must be initiated by creating a pull request in GitHub.
   * A feature branch with specific changes needs to be created.
   * The configuration change needs to be tested locally when possible, or on a development and/or staging sandbox otherwise.
   * The pull request needs to be reviewed before merging the change into the main branch.
3. In all cases, before rolling out the change to production, the engineer must file a ticket describing the change. This ticket must link to the reviewed pull request and/or include a link to the runbook.
4. Once the request has been approved by the CTO, the team member may roll out the change into production environments.

## 9.5 Patch Management Procedures

1. Wally uses automated tooling to ensure systems are up-to-date with the latest security patches.
   * Container images are built from trusted sources.
   * Production systems are patched on every deploy.

## 9.6 Software Development Procedures

1. All development uses feature branches based on the main branch used for the current release. Any changes required for a new feature or defect fix are committed to that feature branch.
   * These changes must be covered under a unit or integration test, where possible.
2. Once the feature and corresponding tests are complete, a pull request will be created. The pull request should indicate which feature or defect is being addressed and should provide a high-level description of the changes made.
3. Code reviews are performed as part of the pull request procedure. Once a change is ready for review, the author(s) will notify other engineers using an appropriate mechanism.
   * Other engineers will review the changes, using the guidelines above.
   * Engineers should note all potential issues with the code; it is the responsibility of the author(s) to address those issues or explain why they are not applicable.
4. Once the review process finishes, each reviewer needs to approve the pull request, at which point the original author(s) may merge their change into the release branch.

## 9.7 Software Release Procedures

1. Software releases are treated as changes to existing systems and thus follow the procedure described in [§9.4](#9.4-changing-existing-systems).
