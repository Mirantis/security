# Mirantis PSIRT Overview

## What is a PSIRT?

> A Product Security Incident Response Team (PSIRT) is an entity within an organization with a core focus on the identification, assessment and mitigation of the risks associated with security vulnerabilities within the products, offerings, solutions, components and/or services which an organization produces and/or sells.

## Mirantis PSIRT Structure

At Mirantis, the PSIRT follows the [distributed model](https://www.first.org/standards/frameworks/psirts/psirt_services_framework_v1.1). It utilizes a small core PSIRT
that works with representatives from the product teams to address security vulnerabilities in products.

The core of the PSIRT has the following responsibilities:

* Creating policies, processes, procedures, and guidelines for the triage, analysis, remediation, and communication of fixes, mitigations or other advisory information to address security vulnerabilities.
* Establishing a matrix of (tiered) product security engineering representatives throughout the organization.  
* Offering leadership and guidance regarding product security vulnerability response and potential risk to the business.
* Acting as the collection point for incoming security vulnerabilities where the economies of scale benefit from a central point of control.
* Notifying the Product Owner/Manager and the security engineer of new security vulnerabilities, assisting in the development of remediation plans, and draft/publish communication of a fix or mitigation, including incident management.

## Vulnerability Handling Process

```
              ┌────────────────────┐
     ┌────────►Vulnerability Report│
     │        └─────────┬──────────┘
     │                  │
     │               ┌──▼───┐
     │               │Triage│
     │               └──┬───┘
     │                  │
     │           ┌──────▼───────┐   No    ┌──────────────┐
     │           │Is Vulnerable?├─────────►Issue Negative│
     │           └──────┬───────┘         │ Response     │
     │                  │ Yes             └──────────────┘
     │                  │
     │             ┌────▼─────┐    Yes    ┌──────────────┐
     │             │Data Leak?├───────────►Report to DPO │
     │             └────┬─────┘           └─────┬────────┘
     │                  │ No                    │
     │                  ◄───────────────────────┘
     │                  │
     │             ┌────▼─────┐   Yes    ┌──────────────────────────┐
     │             │ Public?  ├──────────►Publish Security Advisory │
     │             └────┬─────┘          └─────────┬────────────────┘
     │                  │ No                       │
     │                  │                          │
┌────┴─────┐      ┌─────▼───────┐                  │
│Search For◄──────┤ Development ◄──────────────────┘
│Similar   │      │  Planning   ├───────────┐
└──────────┘      └─────┬───────┘           │
                        │                   │
                        │                   │
                        │                   │
                   ┌────▼─────┐        ┌────▼────┐
                   │ Mitigate │        │Reproduce│
                   └────┬─────┘        └────┬────┘
                        │                   │
                     ┌──▼───┐               │
                     │  CI  ◄───────────────┘
                     └──┬───┘
                        │
                    ┌───▼─────┐
                    │ Release │
                    └───┬─────┘
                        │
            ┌───────────▼───────────────┐
            │ Publish Security Advisory │
            └───────────────────────────┘
```


### Vulnerability Reports

Reports can arrive at the PSIRT via a number of channels

* via psirt@mirantis.com
* from automation which tracks CVEs in third-party dependencies
* from regular third-party penetration tests
* from regular internal penetration tests
* from product teams

When a vulnerability is reported, an acknowledgement of receipt is sent within 24 hours. The team may respond with clarifying questions.


### Triage

The Mirantis PSIRT uses [CVSSv3.1](https://www.first.org/cvss/v3.1/specification-document) to score vulnerabilities. The following qualitative severity ratings are used

| CVSSv3.1 Score | Qualitative Severity Rating |
| :---: | :---: |
| 0.0 | None |
| 0.1 - 3.9 | Low |
| 4.0 - 6.9 | Medium |
| 7.0 - 8.9 | High |
| 9.0 - 10.0 | Critical |

The PSIRT uses the qualitative security rating to set targets for [turnaround of issues](/psirt/targets.md).

### Reporting Data Leaks

Mirantis is ISO 27001 certified and as such has policies and procedures in place for the protection of customer and corporate data. If customer or corporate
data is leaked by a vulnerability, this will be reported to the [Data Protection Officer](mailto:dataprivacy@mirantis.com).

### Development Planning

The Mirantis PSIRT organizes a development team response to a vulnerability. The PSIRT identifies
the key people required to mitigate the vulnerability.

### Reproducing Vulnerability

The Mirantis PSIRT works with development teams to reproduce the vulnerability if possible. Some
classes of vulnerability may be theoretical e.g. crytographic problems but have a clear path
to mitigation and this step may be skipped. For others, it is essential to create test cases
which reproduce the problem so that tests for mitagations can be added to Continuous Integration tests (CI).

### Search for Similar Vulnerabilities

The vulnerability may be the result of a systematic problem. For example, a development group may
be using a technology in the wrong way repeatedly due to misunderstanding, gaps in developer education
or simply that a new class of vulnerability has become apparent.

To address this, the PSIRT will search for similar vulnerabilities or vulnerability patterns and
report findings in the normal vulnerability reporting process. The PSIRT may choose to short-circuit this process and add the new findings to current vulnerability report.

### Mitigate

Mirantis PSIRT will work with development teams to find mitigations. These can be

* workarounds
* improved deployment advice
* runtime changes to a deployed system
* code modifications

### Release

Once any mitagations have been successfully applied, a product release will be scheduled using the
normal development mechanisms. Once the release is public, the PSIRT will publish a security advisory.

### Publish Security Vulnerability

Mirantis PSIRT will publish security vulnerabilities

* in this github repository
* in software release notes
* security bulletins

The PSIRT may opt to co-ordinate disclosure with other parties when the vulnerability impacts multiple vendors.













