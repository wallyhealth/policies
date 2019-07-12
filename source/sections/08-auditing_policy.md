# 8. Auditing Policy

Wally shall audit access and activity of electronic protected health information (ePHI) applications and systems in order to ensure compliance. The Security Rule requires healthcare organizations to implement reasonable hardware, software, and/or procedural mechanisms that record and examine activity in information systems that contain or use ePHI. Audit activities may be limited by application, system, and/or network auditing capabilities and resources. Wally shall make reasonable and good-faith efforts to safeguard information privacy and security through a well-thought-out approach to auditing that is consistent with available resources.

It is the policy of Wally to safeguard the confidentiality, integrity, and availability of applications, systems, and networks. To ensure that appropriate safeguards are in place and effective, Wally shall audit access and activity to detect, report, and guard against:

* Network vulnerabilities and intrusions;
* Breaches in confidentiality and security of patient protected health information;
* Performance problems and flaws in applications;
* Improper alteration or destruction of ePHI;
* Out of date software and/or software known to have vulnerabilities.

This policy applies to all Wally systems that store, transmit, or process ePHI.

## 8.1 Applicable Standards

### 8.1.1 Applicable Standards from the HITRUST Common Security Framework

* 0.a Information Security Management Program
* 01.a Access Control Policy
* 01.b User Registration
* 01.c Privilege Management
* 09.aa Audit Logging
* 09.ac Protection of Log Information
* 09.ab - Monitoring System Use
* 06.e - Prevention of Misuse of Information

### 8.1.2 Applicable Standards from the HIPAA Security Rule

* 45 CFR §164.308(a)(1)(ii)(D) - Information System Activity Review
* 45 CFR §164.308(a)(5)(ii)(B) & &lpar;C&rpar; - Protection from Malicious Software & Log-in Monitoring
* 45 CFR §164.308(a)(8) - HIPAA Security Rule Periodic Evaluation
* 45 CFR §164.312(b) - Audit Controls
* 45 CFR §164.312&lpar;c&rpar;(2) - Mechanism to Authenticate ePHI
* 45 CFR §164.312(e)(2)(i) - Integrity Controls

## 8.2 Auditing Policies

1. Responsibility for auditing information system access and activity is assigned to Wally's Security Officer. The Security Officer shall:
   * Assign the task of generating reports for audit activities to the workforce member responsible for the application, system, or network;
   * Assign the task of reviewing the audit reports to the workforce member responsible for the application, system, or network, the Privacy Officer, or any other individual determined to be appropriate for the task;
   * Organize and provide oversight to a team structure charged with audit compliance activities (e.g., parameters, frequency, sample sizes, report formats, evaluation, follow-up, etc.).
2. Wally's auditing processes shall address access and activity at the following levels listed below. Auditing processes may address date and time of each log-on attempt, date and time of each log-off attempt, devices used, functions performed, etc.
   * User: User level audit trails generally monitor and log all commands directly initiated by the user, all identification and authentication attempts, and data and services accessed.
   * Application: Application level audit trails generally monitor and log all user activities, including data accessed and modified and specific actions.
   * System: System level audit trails generally monitor and log user activities, applications accessed, and other system defined specific actions. Wally utilizes file system monitoring from OSSEC to assure the integrity of file system data.
   * Network: Network level audit trails generally monitor information on what is operating, penetrations, and vulnerabilities.
3. Wally shall log all incoming and outgoing traffic to into and out of its environment. This includes all successful and failed attempts at data access and editing. Data associated with this data will include origin, destination, time, and other relevant details that are available to Wally.
4. Wally utilizes OSSEC to scan all systems for malicious and unauthorized software every 2 hours and at reboot of systems.
5. Wally leverages process monitoring tools throughout its environment.
6. Wally shall identify "trigger events" or criteria that raise awareness of questionable conditions of viewing of confidential information. The "events" may be applied to the entire Wally platform or may be specific to a Customer, partner, business associate or application (See Listing of Potential Trigger Events below).
7. In addition to trigger events, Wally utilizes log correlation functionality to proactively identify and enable alerts based on log data.
8. Logs are reviewed weekly by the Security Officer.
9. Wally's Security Officer and Privacy Officer are authorized to select and use auditing tools that are designed to detect network vulnerabilities and intrusions. These tools may include, but are not limited to:
    * Scanning tools and devices;
    * Password cracking utilities;
    * Network "sniffers."
    * Passive and active intrusion detection systems.
10. The process for review of audit logs, trails, and reports shall include:
    * Description of the activity as well as rationale for performing the audit.
    * Identification of which Wally workforce members will be responsible for review.
    * Frequency of the auditing process.
    * Determination of significant events requiring further review and follow-up.
    * Identification of appropriate reporting channels for audit results and required follow-up.
11. Vulnerability testing software may be used to probe the network to identify what is running (e.g., operating system or product versions in place), whether publicly-known vulnerabilities have been corrected, and evaluate whether the system can withstand attacks aimed at circumventing security controls.
    * Testing may be carried out internally or provided through an external third-party vendor. Whenever possible, a third party auditing vendor should not be providing the organization IT oversight services (e.g., vendors providing IT services should not be auditing their own services - separation of duties).
12. Software patches and updates will be applied to all systems in a timely manner.

## 8.3 Audit Requests

1. A request may be made for an audit for a specific cause. The request may come from a variety of sources including, but not limited to, Privacy Officer, Security Officer, Customer, Partner, or application user.
2. A request for an audit for specific cause must include time frame, frequency, and nature of the request. The request must be reviewed and approved by Wally's Privacy or Security Officer.
3. A request for an audit must be approved by Wally's Privacy Officer and/or Security Officer before proceeding. Under no circumstances shall detailed audit information be shared with parties without proper permissions and access to see such data.
   * Should the audit disclose that a workforce member has accessed ePHI inappropriately, the minimum necessary/least privileged information shall be shared with Wally's Security Officer to determine appropriate sanction/corrective disciplinary action.
   * Only de-identified information shall be shared with Customer or Partner regarding the results of the investigative audit process. This information will be communicated to the appropriate personnel by Wally's Privacy Officer or designee. Prior to communicating with customers and partners regarding an audit, it is recommended that Wally consider seeking risk management and/or legal counsel.

## 8.4 Review and Reporting of Audit Findings

1. Audit information that is routinely gathered must be reviewed in a timely manner, currently weekly, by the responsible workforce member(s). On a quarterly basis, logs are reviewed to assure the proper data is being captured and retained. The following process details how log reviews are done at Wally:
  1. The Security Officer initiates the log review by creating a ticket in the QMS.
  2. The Security Officer, or a Wally engineer assigned by the Security Officer, is assigned to review the logs.
  3. Relevant audit log findings are added to the ticket; these findings are investigated in a later step.
  4. Once the review is completed, the Security Officer approves or rejects the ticket. Relevant findings are reviewed at this stage. If the ticket is rejected, it goes back for further review and documentation. The communications protocol around specific findings are outlined below.
  5. If the ticket is approved, the Security Officer then marks the ticket as Done, adding any pertinent notes required.
2. The reporting process shall allow for meaningful communication of the audit findings to those workforce members, Customers, or Partners requesting the audit.
   * Significant findings shall be reported immediately in a written format. Wally's security incident response form may be utilized to report a single event.
   * Routine findings shall be reported to the sponsoring leadership structure in a written report format.
3. Reports of audit results shall be limited to internal use on a minimum necessary/need-to-know basis. Audit results shall not be disclosed externally without administrative and/or legal counsel approval.
4. Security audits constitute an internal, confidential monitoring practice that may be included in Wally's performance improvement activities and reporting. Care shall be taken to ensure that the results of the audits are disclosed to administrative level oversight structures only and that information which may further expose organizational risk is shared with extreme caution. Generic security audit information may be included in organizational reports (individually-identifiable ePHI shall not be included in the reports).
5. Whenever indicated through evaluation and reporting, appropriate corrective actions must be undertaken. These actions shall be documented and shared with the responsible workforce members, Customers, and/or Partners.
6. Log review activity is monitored on a quarterly basis using the QMS reporting to assess compliance with above policy.

## 8.5 Auditing Customer and Partner Activity

1. Periodic monitoring of Customer and Partner activity shall be carried out to ensure that access and activity is appropriate for privileges granted and necessary to the arrangement between Wally and the 3rd party. Wally will make every effort to assure Customers and Partners do not gain access to data outside of their own domains.
2. If it is determined that the Customer or Partner has exceeded the scope of access privileges, Wally's leadership must remedy the problem immediately.
3. If it is determined that a Customer or Partner has violated the terms of the HIPAA business associate agreement or any terms within the HIPAA regulations, Wally must take immediate action to remediate the situation. Continued violations may result in discontinuation of the business relationship.

## 8.6 Audit Log Security Controls and Backup

1. Audit logs shall be protected from unauthorized access or modification.
2. All audit logs are protected in transit and encrypted at rest to control access to the content of the logs.
3. Audit logs shall be stored on a separate system to minimize the impact auditing may have on the privacy system.
   * Separate systems are used to apply the security principle of "separation of duties" to protect audit trails from hackers.

## 8.7 Workforce Training, Education, Awareness and Responsibilities

1. Wally workforce members are provided training, education, and awareness on safeguarding the privacy and security of business and ePHI. Wally's commitment to auditing access and activity of the information applications, systems, and networks is communicated through new employee orientation, ongoing training opportunities and events, and applicable policies. Wally workforce members are made aware of responsibilities with regard to privacy and security of information as well as applicable sanctions/corrective disciplinary actions should the auditing process detect a workforce member's failure to comply with organizational policies.

## 8.8 External Audits of Information Access and Activity

1. Prior to contracting with an external audit firm, Wally shall:
   * Outline the audit responsibility, authority, and accountability;
   * Choose an audit firm that is independent of other organizational operations;
   * Ensure technical competence of the audit firm staff;
   * Require the audit firm's adherence to applicable codes of professional ethics;
   * Obtain a signed HIPAA business associate agreement;
   * Assign organizational responsibility for supervision of the external audit firm.

## 8.9 Retention of Audit Data

1. Audit logs shall be maintained for a period of six years.
2. Reports summarizing audit activities shall be retained for a period of six years.
3. Audit log data is retained in the audit log system for either 30 or 400 days, depending on the type of the data. Beyond that, log data is encrypted and moved to cold storage.

## 8.10 Potential Trigger Events

* High risk or problem prone incidents or events.
* Business associate, customer, or partner complaints.
* Known security vulnerabilities.
* Atypical patterns of activity.
* Failed authentication attempts.
* Remote access use and activity.
* Activity post termination.
* Random audits.
