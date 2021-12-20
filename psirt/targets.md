# PSIRT Turnaround Times

The Mirantis PSIRT aims to complete triage and
inform the reporter of severity and next steps within
48 hours of receiving a report.

Targets for remediation of a vulnerability are

| Severity | Remediation Target |
|----------|--------------------|
| Critical | Patch/mitigation ready for test within 48 hours |
| Medium/High | Patch/mitigation ready for test within 7 days |
| Low | Patch/mitigation for next scheduled maintenance release sprint |

These are _internal targets for the PSIRT_ and do not constitute a Service Level Agreement or
a binding contract.

# Patch Releases

Mirantis uses a monthly patch release to deliver fixes to security vulnerabilities and bugs. Critical vulnerabilities may require
a hotfix, workaround or patch release outside of the normal monthly release. The upper bound on time between discovery and a patch release/hotfix is
as follows.

|Severity | Time Limit |
|---------|-------------|
| Critical| 7 days |
| High    | 30 days |
| Medium  | 60 days  |
| Low     | 90 days  |
