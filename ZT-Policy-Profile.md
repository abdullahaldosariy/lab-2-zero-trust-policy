# 1. ZTA Component Definitions (20 Points)

## Policy Engine (PE)
For me, the Policy Engine is the brain of Zero Trust. It uses policy rules plus current signals (identity, device, and network context) to decide if access should be granted, denied, or revoked.

## Policy Administrator (PA)
The Policy Administrator is the rule setter and translator. It converts PE decisions into real actions by setting up or blocking the communication path and handling session authorization.

## Policy Enforcement Point (PEP)
The Policy Enforcement Point is the gatekeeper in front of the resource. It sits in the traffic path and enforces what the policy system decided by allowing, denying, monitoring, or terminating access.

# 2. Core Principle Application (15 Points)

Chosen Principle: **Verify Explicitly**

In my design for this facility, I am applying **Verify Explicitly**. If an HR specialist tries to open the Employee PII Database, the Policy Engine does not trust the request by default, even when the person is already inside the company network.

The PE checks MFA status, confirms the employee is in the correct HR role, verifies endpoint posture (managed + patched + EDR healthy), and validates network source (approved subnet or approved VPN). If one signal fails, access is denied or step-up controls are required. This matches Verify Explicitly because every request is evaluated using current identity, device, and network evidence.

# 3. Simplified Policy Table (10 Points)

| Policy Requirement (Signal) | Condition to be Met by User | Action if Condition is Met |
| --- | --- | --- |
| User Identity | User signs in with MFA and is in the approved HR role/group for PII data. | Grant Access when identity checks pass. |
| Device Posture | Device is company-managed, encrypted, and has current patch and EDR compliance. | Grant Access when device posture checks pass. |
| Network Context | Request comes from an approved facility subnet or approved corporate VPN endpoint. | Grant Access when network checks pass and other required signals are valid. |

# 4. Submission Details (5 Points)

# Git Repository Metadata

Project: Lab 2 - Zero Trust Policy

Filename: ZT-Policy-Profile.md

Commit Message: Add ZT policy profile for Golden State Water Treatment Facility - https://github.com/abdullahaldosariy/lab-2-zero-trust-policy

Due Date: March 2, 2026

Sources (.edu/.org):
- https://er.educause.edu/articles/2024/8/implementing-zero-trust-architecture-for-campus-security
- https://library.educause.edu/topics/cybersecurity-and-privacy/zero-trust
- https://digitalprivacy.ieee.org/publications/topics/articles/3717-zero-trust-architecture
