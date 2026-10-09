# Authorized Security Lab — Data-Flow Diagram

## 1. Purpose
This document describes the expected data flows in the authorized security lab. The diagram is conceptual and must be verified against the actual lab configuration.

## 2. Components
- Tester: The authorized assessor performing lab activities.
- Local training web app: 127.0.0.1:8080.
- Deliberately vulnerable VM: 192.168.56.20.

## 3. Conceptual Data Flow

    [Authorized Tester]
            |
            | HTTP requests (confirm actual route)
            v
    [Local Training Web App]
            |
            | Further communication, if configured
            v
    [Vulnerable VM]

Note: The relationship and communication between the web app and VM are not confirmed by the supplied inventory. Verify the actual architecture before treating this as an implemented connection.

## 4. Trust Boundaries
- Tester to local web app: boundary between testing activity and the application.
- Host machine to virtual machine: boundary between the host and the isolated lab network, if the VM uses host-only networking.
- Any connection to external systems is out of scope unless explicitly authorized.

## 5. Data Types
- Test requests and responses.
- Synthetic test data.
- Security findings and redacted evidence.
- No real personal data or production credentials should be used.

## 6. Security Considerations
- Confirm each target against the approved asset inventory.
- Restrict access to the lab network.
- Do not expose the vulnerable VM to the public internet.
- Stop testing if unexpected traffic or access outside the approved scope occurs.

## 7. Verification Needed
- Confirm how the web app communicates with the VM, if at all.
- Confirm the VM network mode and allowed ports.
- Update this document to match the verified lab configuration.

## 8. Status
Conceptual draft — pending verification against the actual lab setup.
