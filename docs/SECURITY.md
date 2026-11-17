# BhuGrid 1.0 — Security and Access Control Overview

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**Platform:** GIS-based Religious Institution and Asset Management Platform  
**Security Platform:** Supabase Authentication and PostgreSQL Access Controls  
**Development Stage:** Functional Prototype / Controlled DEMO  
**Publication Status:** Pending Backend and Security Review

---

## 1. Security Overview

BhuGrid 1.0 incorporates authentication and role-aware authorization to protect institutional information and support controlled access to its management workflows.

The security architecture is designed around three principles:

1. **Authenticated Access:** Protected institutional workflows require approved user accounts.
2. **Role-Based Authorization:** Users can access functions appropriate to their assigned roles.
3. **Institution-Specific Data Isolation:** Institutional stakeholders should access only the institutions, properties and assets assigned to them.

The documented prototype uses Supabase Authentication, PostgreSQL access controls and server-side authorization mechanisms.

Security testing reported by the project team applies to the controlled prototype and does not constitute independent production security certification.

## 2. Supabase Authentication

BhuGrid uses **Supabase Auth** to manage authenticated access to protected application functionality.

### 2.1 Authentication Requirements

The documented stakeholder authentication model includes:

- Administrator-provisioned stakeholder accounts.
- Approved user access.
- No public stakeholder self-registration.
- No anonymous stakeholder sign-in.
- Authenticated sessions for protected institutional workflows.

Authentication establishes user identity. It does not independently authorize access to every institution or record.

### 2.2 Authentication and Authorization Separation

The system conceptually separates:

| Security function | Responsibility |
|---|---|
| Authentication | Confirms the identity of a signed-in user |
| Role authorization | Determines which application functions the user may access |
| Institution assignment | Determines which institutional records a stakeholder may access |
| Database authorization | Restricts protected data operations |
| Administrative review | Requires authorized human assessment and decisions |

This separation helps prevent authentication alone from granting unrestricted access to institutional information.

## 3. Approved User Roles

BhuGrid supports stakeholder, Inspector and Administrator workflows.

### 3.1 Institutional Stakeholders

The Institutional Stakeholder Portal serves three categories:

1. **Local Bodies**
2. **Trustees / Institutional Management**
3. **Government Agencies**

Stakeholder access is based on approved accounts and institutional assignments.

Stakeholders are intended to view only their permitted institutions and associated property and asset records.

### 3.2 Inspector

Inspectors use authorized workflows for:

- Recording field observations.
- Submitting inspection information.
- Associating available location information with observations.
- Providing supporting evidence.
- Accessing inspection functions permitted by their role.

Inspector access does not automatically provide unrestricted administrative privileges.

### 3.3 Administrator

Administrators use authorized workflows for:

- Reviewing institutional and inspection information.
- Monitoring submitted observations.
- Evaluating possible-change reports.
- Recording permitted administrative decisions.
- Managing approved access and assignments through supported administrative processes.

Administrative privileges must remain restricted to appropriately authorized users.

## 4. Role-Based Authorization

Role-based authorization determines which operations are permitted for different categories of users.

### 4.1 Conceptual Access Matrix

| Function | Stakeholder | Inspector | Administrator |
|---|---|---|---|
| Authenticated sign-in | Approved accounts | Authorized accounts | Authorized accounts |
| View assigned institutions | Yes | As permitted | As permitted |
| View linked property and asset information | Assigned records only | As permitted | As permitted |
| Submit inspection observations | Not a standard stakeholder function | Yes | According to authorized workflow |
| Review inspection submissions | Limited to permitted views | According to role | Yes |
| Record administrative decisions | No | No | Yes |
| Manage institutional access assignments | No | No | Authorized administrative process |
| Use stakeholder-support tools | Yes, where enabled | As permitted | As permitted |

This matrix describes the intended role model. It does not disclose exact database permissions or guarantee that every possible access combination has been independently tested.

### 4.2 Least-Privilege Principle

The authorization design follows the principle that users should receive only the access required for their assigned responsibilities.

A stakeholder's membership in one institution must not automatically authorize access to another institution.

## 5. Institution-Specific Data Isolation

Institution-specific data isolation is a central requirement of the Institutional Stakeholder Portal.

### 5.1 Assignment Model

The conceptual access relationship is:

```text
Authenticated Stakeholder
          |
   Approved Membership
          |
 Institution Assignment
          |
  Assigned Institution
          |
  +-------+-------+
  |               |
Properties       Assets
  |               |
  +-------+-------+
          |
 Authorized Access
```

The model is designed to ensure that:

- Stakeholders access assigned institutions.
- Linked property and asset information follows institution-level authorization.
- Unassigned institutional records remain inaccessible.
- Cross-institution access attempts are denied.

### 5.2 Verification Status

The project team reported that Shakti's backend verification on **16 November 2026** passed checks covering:

- Approved stakeholder membership and assignment.
- Assigned institution visibility.
- Institution-linked property and asset restrictions.
- Cross-institution access denial.
- Separation of stakeholder, Inspector and Administrator access.

**Reported status: PASS — controlled prototype checks.**

This is a team-reported verification result, not an independent security audit. Shakti must confirm the wording and evidence before this document is published.

## 6. Row-Level Security and Server-Side Access Control

Supabase PostgreSQL supports Row-Level Security (RLS) and authorization-controlled database operations.

### 6.1 Row-Level Security Principles

RLS is used to restrict access to protected records according to relevant authorization conditions.

The documented access-control approach includes:

- Authenticated access requirements.
- Role-aware record permissions.
- Institution-specific record restrictions.
- Protection against unauthorized cross-institution reads.
- Controlled access to linked property and asset information.

### 6.2 Server-Side Authorization

Protected operations should enforce authorization on the backend rather than relying only on frontend interface restrictions.

This is important because hiding an interface element does not, by itself, prevent unauthorized requests.

Server-side authorization principles include:

- Validating authenticated user context.
- Checking permitted roles and institutional assignments.
- Restricting access to protected database operations.
- Preventing unauthorized access through modified requests.
- Keeping privileged operations outside unrestricted client access.

The project's reported backend verification included RLS and authorized database-operation checks.

**Implementation boundary:** Exact RLS policies, SQL functions, internal permission rules and security configuration are intentionally excluded from this public document.

## 7. API Key and Credential Protection

BhuGrid integrates external services including Groq and Geoapify.

### 7.1 Protected External Integrations

The documented architecture uses Supabase Edge Functions to support external service requests.

External service credentials should remain in protected server-side configuration rather than being embedded in public frontend code.

| Integration | Security consideration |
|---|---|
| Groq AI | Protect API credentials and restrict permitted application requests |
| Geoapify Places API | Protect service credentials and control API usage |
| Supabase | Distinguish public client configuration from privileged server credentials |
| Render | Protect deployment settings and environment-specific secrets |

### 7.2 Credential Handling Requirements

The project should follow these principles:

- Do not publish API keys, tokens or passwords.
- Do not commit privileged credentials to public repositories.
- Keep server-side secrets outside frontend bundles.
- Restrict access to privileged backend operations.
- Rotate exposed credentials if a disclosure occurs.
- Review repository files and Git history before public release.

This documentation does not reveal actual environment variable values, authentication tokens or internal service configurations.

## 8. Human Approval and Administrative Decision Security

BhuGrid includes AI-assisted administrative review and rule-based DEMO prioritization.

These tools are intended to support human assessment rather than replace authorized decision-making.

### 8.1 Administrative Decision Principles

- AI-generated observations are advisory.
- Rule-based prioritization is a DEMO indicator.
- Inspection evidence requires human assessment.
- Possible-change observations are not automatically confirmed violations.
- Administrative decisions remain under authorized human control.
- AI output must not independently establish property ownership, encroachment or legal liability.

### 8.2 Review Accountability

The conceptual workflow is:

```text
Inspector Observation
         |
Supporting Evidence
         |
Administrative Review
         |
Optional AI Assistance
         |
Human Assessment
         |
Authorized Decision
```

AI output is supporting information, not an autonomous approval mechanism.

## 9. Known Security Limitations

BhuGrid 1.0 is a controlled development prototype.

Its documented security limitations include:

- No independent penetration-testing certification.
- No comprehensive production security audit.
- No demonstrated statewide operational security assurance.
- No verified integration with official government identity systems.
- Limited testing coverage compared with production requirements.
- Dependence on external hosting and API services.
- Future need for stronger monitoring, audit procedures and incident response.
- Additional privacy and data-governance requirements before using real institutional information.

The successful completion of prototype authorization checks does not establish protection against every possible attack or configuration error.

## 10. Security Verification and Future Requirements

### 10.1 Documented Prototype Verification

| Security area | Reported status |
|---|---|
| Supabase authentication | PASS — team-reported |
| Approved stakeholder account access | PASS — team-reported |
| Public signup and anonymous sign-in restrictions | PASS — team-reported |
| Institution-specific assignments | PASS — team-reported |
| Cross-institution access denial | PASS — team-reported |
| Linked property and asset restrictions | PASS — team-reported |
| Inspector and Administrator role separation | PASS — team-reported |
| Independent penetration testing | Not established |
| Production security certification | Not established |

### 10.2 Future Security Priorities

Before real-world institutional deployment, priorities include:

1. Independent authorization and penetration testing.
2. More comprehensive negative-access and privilege-escalation tests.
3. Formal security monitoring and incident response procedures.
4. Credential rotation and access-review procedures.
5. Privacy and data-retention governance.
6. Approved institutional data onboarding.
7. Backup, recovery and operational security validation.

These are future requirements, not completed BhuGrid 1.0 certifications.

## 11. Related Documentation

- [Project Overview](../README.md)
- [Product Requirements Document](PRD.md)
- [System Architecture](ARCHITECTURE.md)
- [Data Model Overview](DATABASE.md)
- [Features and Future Implementation](../FEATURES_AND_FUTURE_IMPLEMENTATION.md)

---

## 12. Publication and Security Review

**Required Reviewer:** Shakti Saranjana Pradhan — Backend, Database and Security.

**Review Status:** Pending explicit approval.

Before publication, the reviewer must confirm:

- Authentication and authorization descriptions reflect the actual prototype.
- Stakeholder isolation test results are accurately represented.
- RLS and server-side access-control claims match implemented behavior.
- No private policies, credentials, tokens or sensitive account details are exposed.
- No unsupported production security claims are included.

**Repository Notice — Documentation Only**

This public repository contains BhuGrid 1.0 project documentation only. It does not publish or license the original application source code, private backend implementation, internal database policies, authentication credentials, deployment secrets or sensitive institutional records.

**Security Status:** Prototype-level access-control checks have been reported as passing. Independent security certification and production-readiness verification have not been established.
