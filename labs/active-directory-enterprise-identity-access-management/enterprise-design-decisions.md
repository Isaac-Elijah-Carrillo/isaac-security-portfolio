# Enterprise Design Decisions

This document explains the architectural and administrative decisions made throughout this Identity & Access Management lab.

---

# Why Create Custom Organizational Units?

Although Active Directory includes default **Users** and **Computers** containers, enterprise environments typically organize directory objects into custom Organizational Units (OUs).

Benefits include:

- Logical organization
- Simplified administration
- Group Policy targeting
- Administrative delegation
- Scalability

Department-based OUs also mirror the structure of the business, making administration easier as the environment grows.

---

# Why Manage Identities Through Active Directory?

Active Directory serves as the central identity provider for users, computers, and security principals within the domain.

Centralized identity management provides:

- Consistent authentication
- Simplified account administration
- Centralized policy enforcement
- Easier auditing
- Improved security

---

# Why Use Security Groups?

Permissions should be assigned to Security Groups rather than individual users.

This approach supports Role-Based Access Control (RBAC) by granting permissions based on job responsibilities instead of specific individuals.

Benefits include:

- Easier onboarding
- Easier offboarding
- Simplified department transfers
- Reduced administrative overhead
- Consistent permission management
- Principle of Least Privilege

---

# Authentication vs Authorization

Authentication answers:

> **Who are you?**

Authorization answers:

> **What are you allowed to access?**

Authentication occurs before authorization.

A successfully authenticated user may still be denied access if they are not authorized through the appropriate Security Group membership.

---

# Why Disable Accounts Instead of Deleting Them?

Disabling user accounts preserves important enterprise information while preventing access.

Benefits include:

- Audit history
- Security Identifier (SID)
- File ownership
- Compliance records
- Easier account restoration

Deleting accounts permanently removes these associations.

---

# Why Populate User Attributes?

Enterprise directories are more than authentication databases.

User attributes support:

- Outlook Global Address List
- Microsoft Teams
- Organizational charts
- Internal directory searches
- Administrative reporting
- Identity management platforms

Maintaining accurate identity information improves operational efficiency across the organization.

---

# Why Configure Manager Relationships?

The Manager attribute establishes reporting relationships between users.

Benefits include:

- Organizational hierarchy
- Reporting structures
- Enterprise workflows
- Microsoft 365 organizational charts
- Directory visibility

Although optional, maintaining accurate manager relationships reflects real-world enterprise identity management.

---

# Lessons Learned

This project reinforced several foundational Identity & Access Management concepts:

- Designing scalable Active Directory structures
- Managing enterprise identities
- Implementing Role-Based Access Control (RBAC)
- Understanding Authentication vs Authorization
- Organizing identities through Organizational Units
- Managing Security Groups
- Validating domain authentication

These concepts establish the foundation for future work with Group Policy, Microsoft Entra ID, hybrid identity, and enterprise access management.
