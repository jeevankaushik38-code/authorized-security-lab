# Authorized Security Lab — STRIDE Threat Model

## 1. Purpose
This document identifies potential threats to the authorized security lab using the STRIDE framework. These are preliminary threat scenarios, not confirmed vulnerabilities.

## 2. Assets in Scope
- Local training web app: 127.0.0.1:8080
- Deliberately vulnerable VM: 192.168.56.20

Only assets explicitly authorized in the asset inventory are in scope.

## 3. Threat Register

| ID | STRIDE Category | Potential Threat | Impact | Initial Risk | Mitigation |
|---|---|---|---|---|---|
| T01 | Spoofing | An unauthorized user impersonates a legitimate test account. | Unauthorized access | Medium | Use dedicated test accounts and appropriate authentication controls. |
| T02 | Tampering | An attacker modifies application input or stored test data. | Data integrity loss | Medium | Validate inputs and restrict write access. |
| T03 | Repudiation | Lab actions cannot be attributed because audit records are missing. | Incomplete investigation | Low | Maintain appropriate logs and timestamps. |
| T04 | Information Disclosure | Debug output or responses expose sensitive test information. | Confidentiality loss | Medium | Use synthetic data, redact secrets, and restrict access. |
| T05 | Denial of Service | Excessive requests make the lab service unavailable. | Lab disruption | High | Prohibit DoS testing and use conservative request rates. |
| T06 | Elevation of Privilege | A user gains permissions beyond their intended lab role. | Unauthorized control | High | Apply least privilege and review permissions. |

## 4. Risk Rating Notes
These ratings are preliminary qualitative estimates. Confirm likelihood and impact against the actual lab configuration and assessment requirements.

- Low: Limited expected impact.
- Medium: Meaningful impact requiring mitigation.
- High: Significant potential impact requiring priority attention.

## 5. Trust Boundaries
- Authorized tester to local training web app.
- Host machine to virtual machine, depending on the verified network configuration.
- Any external system is outside scope unless explicitly authorized.

## 6. Recommended Safeguards
- Keep the vulnerable environment isolated.
- Use synthetic data and dedicated test accounts.
- Restrict access to authorized users.
- Keep evidence minimal and redact sensitive values.
- Stop testing if unexpected disruption or out-of-scope access occurs.

## 7. Limitations
The threats above are hypothetical scenarios for planning. No vulnerability has been confirmed by this document alone. The actual application architecture and security controls must be verified before final risk ratings are assigned.

## 8. Status
Preliminary threat model — review and validate against the actual lab before assessment.
