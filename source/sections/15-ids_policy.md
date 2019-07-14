# 15. IDS Policy

In order to preserve the integrity of data that Wally stores, processes, or transmits for Customers, Wally implements strong intrusion detection tools and policies to proactively track and retroactively investigate unauthorized access. Wally utilizes tools that track file system integrity, monitor log data, and detect rootkit access.

## 15.1 Applicable Standards

### 15.1.1 Applicable Standards from the HITRUST Common Security Framework

* 09.ab - Monitoring System Use
* 06.e - Prevention of Misuse of Information
* 10.h - Control of Operational Software

### 15.1.2 Applicable Standards from the HIPAA Security Rule

* 164.312(b) - Audit Controls

## 15.2 Intrusion Detection Policy

1. Log data is monitored and correlated from different systems on an ongoing basis. Generated reports are reviewed by the Security Officer on a weekly basis.
2. Alerts are generated to analyze and investigate suspicious activity or suspected violations.
3. File system integrity is monitored and real time alerts are sent when suspicious changes are made to the file system.
4. Automatic monitoring is done to identify patterns that might signify the lack of availability of certain services and systems (DoS attacks).
5. Wally firewalls monitor all incoming traffic to detect potential denial-of-service attacks. Suspected attack sources are blocked automatically. Additionally, our hosting provider actively monitors its network to detect denial-of-service attacks.
6. All new firewall rules and configuration changes are tested before being pushed into production. All firewall and router rules are reviewed every quarter.
