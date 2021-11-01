# Mirantis PSIRT Training

## PSIRT Operational Training

**Mandatory** training for PSIRT members: https://learning.first.org/courses/course-v1:FIRST+PSIRT+2018/about

## Triage

Learning outcomes:

* understand CVSSv3.1
* become confident in scoring a large variety of vulnerabilities
* understand the part of triage in the overall PSIRT process
* understand which domain expertise to build

Reports of vulnerabilities need to be triaged. At Mirantis, we use CVSSv3.1 to score vulnerabilities.
It is important that the ability to score vulnerabilities in a repeatable (the same incident handler gets
consistent scores for similar bugs) and uniform (different handlers get similar scores for the same bug).
To achieve this, all PSIRT members **must** complete the CVSS training here: https://learning.first.org/courses/course-v1:FIRST+CVSSv3.1+2020/about.

All reports will be scored: if the score comes out at zero, it's not a security vulnerability.
If the qualitative severity rating is "Low", it is at the discretion of the PSIRT to label a report
a security vulnerability. Factors which play a role here are:

* customer perception
* customer regulatory requirements
* if the reported issue may be indicative of an area that needs further investigation

Qualitative security ratings of "Medium", "High" and "Critical" will always be dealt with as vulnerabilities.

To accurately triage, PSIRT members need to understand key areas in computer security and the Mirantis product line.
Security topics include

* practical cryptography usage
* web application security
* kubernetes security
* container security
* secure operation of cloud services
* Linux security mitigations using SELinux, apparmor, and admin best practices

To build competency, members are encouraged to complete the following:

* [cryptopals](https://cryptopals.com/)
* [Port Swigger Academy](https://portswigger.net/web-security)
* [CN330: Advanced Kubernetes Security](https://training.mirantis.com/courses/cn330-advanced-kubernetes-security/)

Team members should complete courses at https://training.mirantis.com/courses/ to build familiarity with the Mirantis product line.


## Identifying Data Leaks

Learning outcomes:

* know what Personally Identifiable Information is
* have a clear idea of what is customer and corporate data


Personal Data is defined differently in different jurisdictions and is governed by different laws.
The following resources will help build an understanding of what is meant by personal data.


* In the EU: https://gdpr.eu/eu-gdpr-personal-data/
* In the US: https://www.dhs.gov/privacy-training/what-personally-identifiable-information

If in doubt, ask the Data Protection Office at dataprivacy@mirantis.com.

Customer and corporate data may be
* Personal Data about a customer, Mirantis employees etc
* Financial information: price lists, invoices, bank details etc
* Intellectual Property: designs, source code etc

If a vulnerability leaks information which may fall into the above categories, contact the Data Protection Officer
at dataprivacy@mirantis.com. If in doubt, **ask the Data Protection Officer**.







