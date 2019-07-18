# 1. Introduction

Wally Health, Inc. ("Wally") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of Patients and Dentists (collectively, "Customers" or "Customer"). Wally strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by Wally to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for Wally Customers.

## 1.1 Platform

Wally makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of Customer data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, intrusion detection and prevention, etc).

## 1.2 Compliance Inheritance

Wally signs business associate agreements (BAAs) with Dentists. These BAAs outline Wally's obligations and liability in the case of a breach. In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, Wally manages various aspects of compliance for Dentists. The aspects of compliance that Wally manages for Dentists are inherited by Dentists, and Wally assumes the risk associated with those aspects of compliance. In doing so, Wally helps Dentists achieve and maintain compliance, as well as mitigates Dentists' risk.

Certain aspects of compliance cannot be inherited. Because of this, Dentists, in order to achieve full compliance, must implement certain organizational policies. These policies and aspects of compliance fall outside of the services and obligations of Wally.

Mappings of HIPAA Rules to Wally controls and a mapping of what Rules are inherited by Dentists are covered in [§2](#2.-hipaa-inheritance).

## 1.3 Wally Organizational Concepts

The physical infrastructure environment is hosted at [Google Cloud Platform](https://cloud.google.com/) (GCP). The network components and supporting network infrastructure are contained within GCP and managed by GCP. Wally does not have physical access into the network components.

Within the Wally Platform on GCP, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, etc. Wally assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption. The encryption standards are maintained in line with NIST best practices.

The data and network segmentation in GCP is achieved by using a dedicated Virtual Private Cloud (VPC). The segmentation strategies employed by Wally effectively create RFC 1918, or dedicated, private segmented and separated network and IP spaces.

Additionally, each server is configured to restrict access to only justified ports and protocols. Wally has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over a Transport Layer Security (TLS) encrypted session.

The Virtual Private Network (VPN) server and application servers are externally facing and accessible via the Internet. The database servers, where the ePHI resides, are located on the internal Wally network. Access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business-justified reason. Remote access to internal servers is not accessible except through load balancers.

All components are tested end-to-end for usability, security, and impact prior to deployment to production.

## 1.4 Requesting Audit and Compliance Reports

Wally, at its sole discretion, shares audit reports, on a case by case basis. All audit reports are shared under explicit Non-Disclosure Agreement (NDA) between Wally and party to receive materials. Audit reports can be requested by Wally workforce members on behalf of or directly by Wally Customers.

The following process is used to request audit reports:

1. Email is sent to the Wally Security Officer.
2. The Security Officer will log an issue with the details of the request into the Wally Quality Management System (QMS). The QMS is used to track requests' status and outcomes.
3. The Security Officer will confirm if a current NDA is in place with the party requesting the audit report. If there is no NDA in place, the Security Officer will send one for execution.
4. Once it has been confirmed that an NDA is executed, the Security Officer will approve the issue.
5. If the Issue is rejected, the Security Officer will notify the requesting party that we cannot share the requested report.
6. If the issue has been approved, the Security Officer will send the customer the requested audit report and complete the QMS issue for the request.

## 1.5 Version Control

Refer to the GitHub repository at [https://github.com/wallyhealth/policies](https://github.com/wallyhealth/policies) for the full version history of these policies.
