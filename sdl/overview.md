# Mirantis Secure Development Lifecycle (MSDL) Overview

The Mirantis Secure Development Lifecycle (MSDL) is a methodology for ensuring that security is considered throughout the software development process.
Mirantis development teams use a variety of development processes and the MSDL is flexible enough to fit the needs of all teams. The PSIRT works
closely with each team to implement the MSDL, measure its success and improve processes based on metrics and compliance reporting.

# Mirantis SDL Practices

Each team works with the PSIRT to integrate the following SDL practices.

## Provide Security Training

All staff must complete security training. This training is tailored to the individual, team and product but must include the [Mirantis Baseline Security Training](/sdl/baseline-training.md).
For example, developer training should include language and technology specific training. Teams should work with the PSIRT to establish what is best practice, identify emerging threats 
and areas of improvement identified by metrics and compliance reporting.

## Define Security Requirements

Development teams, and program and product managers must understand the security requirements for the products they create and maintain. Requirements can be derived from

* customers
* legal considerations
* industry standards
* internal security standards
* threat intelligence from PSIRT
* reviews of previous vulnerabilities

The optimal time to capture requirements is at the beginning of development of a feature. However, security requirements need to be updated throughout the project's lifetime to reflect
changes in threats.
 
## Define Metrics and Compliance Reporting 

Security quality needs to be measured. Teams should identify security vulnerabilities and score them with CVSSv3.1. Meaningful security bug bars should be set e.g. time bounds for each qualitative
severity level should be set for fixing security defects. Security defects should be tracked in the project's normal bug tracker but be clearly labelled for easy collection of security metrics.
 
## Perform Threat Modeling

During development of features, threat modelling should be used as it

* is cheap to perform compared to defect remediation
* can help identify mitigations
* makes excellent documentation for the PSIRT when responding to incidents
 
## Use Security Primitives Safely and Consistently

In the secure design and implementation of features, it is often the case that "security primitives" (e.g. cryptography, identification and authorization, audit logging etc) are selected and
implemented. This is notoriously error prone and often leads to vulnerabilities. Design requirements for security primitives which ensure safe and consistent reuse of secure implementations
should be established.
 
## Define and Use Cryptography Standards

Standards must be defined for when and how to use cryptography. Cryptography should be used to protect sensitive data from unintended disclosure or modification. Industry-vetted cryptographic
libraries should be used to provide cryptographic primitives. Don't roll your own cryptography.

*Mirantis has FIPS 140-2 compliant cryptographic libraries which should be used where possible.*
 
## Manage the Security Risk of Using Third-Party Components

Any third-party component, open-source or otherwise, must be monitored for security vulnerabilities. Bugs in third-party code should be tracked using the system for bugs in in-house code. Patches should be applied with the same severity-based priority as used
for in-house code. Mirantis has tools for dependency and container scanning which should be employed by all teams.
 
## Use Approved Tools

Teams should establish a common set of approved tools and create a consistent development environment. Compilers, linkers etc and secure development tools like security linters should be kept up to date to take advantage of
technology improvements.
 
## Perform Static Analysis Security Testing (SAST)

Static analysis tools should be used to identify security bugs. An investment of developer time is often required to configure static analysis tools to avoid false-positives: this is a good
investment. Clear standards should be set for the number of warnings a project is allowed to have before shipping.
 
## Perform Dynamic Analysis Security Testing (DAST)

Adversarial testing of running systems should be performed to find bugs as early as possible in the development cycle. Options include

* fuzzing
* fault-injection
* web application security scanners

## Perform Penetration Testing

Penetration tests should be performed by internal security teams and followed up on a regular basis by independent third-parties.
 
## Integrate with the PSIRT

Teams should integrate with the Mirantis PSIRT. The following information should be shared with the PSIRT

* points of contact
* threat models
* design documents

The team should work with the PSIRT to learn how to best respond to a security incident. The preparedness of the team should be tested regularly with simulated vulnerabilities.


