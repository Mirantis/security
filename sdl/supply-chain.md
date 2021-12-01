# Mirantis Supply Chain Security

## Introduction

Mirantis leverages open-source libraries and packages. Detecting, tracking and
fixing security vulnerabilities in this code is a massive undertaking. Recently,
open source packages have been targeted as a means to inject malicious code
into [downstream projects](https://snyk.io/blog/npm-security-malicious-code-in-oss-npm-packages/).

The culture at Mirantis with regards to third-party components is:

> if you ship it, you own it

That is, vulnerabilities in open-source and third-party dependencies are treated
in the same way as vulnerabilities in in-house code.

## Bill of Materials

The first step to supplying the software supply chain is _knowing what you have_.
Mirantis maintains a _bill of materials_ (BoM) for each product and stores
dependencies in source control.

## Automation

Getting timely notification of vulnerabilities in open-source dependencies
is not possible with manual searches. Most products include hundreds if not
thousands of dependencies across different technology domains e.g frontend javascript,
server container code etc. Each dependency will pull in dependencies of its own.

To manage the "firehose" of CVE information, Mirantis uses

* [whitesource](https://www.whitesourcesoftware.com)
* [dependabot](https://github.com/dependabot)

to automate the detection and remediation of upstream vulnerabilities.

PSIRT are looped in to triage vulnerabilities with [qualitative severity](/psirt/overview.md#triage) HIGH or
greater.

