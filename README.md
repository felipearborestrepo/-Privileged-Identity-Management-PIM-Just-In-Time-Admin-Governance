# 🔐 Privileged Identity Management (PIM) — Just-In-Time Admin Governance

<img width="1536" height="1024" alt="ChatGPT Image Feb 13, 2026 at 11_30_04 PM" src="https://github.com/user-attachments/assets/1cff7e3d-7d43-4fe4-b276-88c139cf6791" />

**Platform:** Microsoft Entra ID  
**Focus:** Privileged Access Governance • Least Privilege • Zero Trust  
**Scope:** Cloud-only privileged role lifecycle  
**Outcome:** Implemented just-in-time elevation with controlled activation, early privilege removal, and audit validation.

---

## 📘 Project Overview

This project demonstrates how privileged access can be governed using Microsoft Entra Privileged Identity Management (PIM) by replacing standing administrative permissions with **eligible assignments** that require activation.

A dedicated test identity was used to simulate real administrative workflows, including:

- Activating a privileged role with MFA and justification
- Using temporary elevation for administrative tasks
- Removing privileged access shortly after activation
- Reviewing audit evidence for role lifecycle events

This reflects how organizations enforce **least privilege** and reduce the risk associated with permanent admin access.

---

## 🎯 Objectives

- Eliminate standing administrative access
- Configure eligible role assignment
- Require MFA and justification for elevation
- Activate role temporarily
- Remove privilege shortly after activation
- Validate governance using audit logs

---

## 🏗️ Environment

- Microsoft Entra ID tenant
- Privileged Identity Management enabled
- Cloud-only test identity
- Break-glass admin excluded from governance controls

---

## 👤 Identity Preparation

A dedicated administrative test account was created:

- `Felipe-PIM`

This allowed privileged operations to be tested without impacting primary administrative identities.

📸 Evidence:

![Image 2-13-26 at 23 04](https://github.com/user-attachments/assets/0faf2caa-b921-47a5-b6fa-6752dc82a715)

A break-glass account remained available to prevent tenant lockout scenarios.

---

## 🔐 Role Governance Configuration

The **Global Administrator** role was configured to remove standing access and require activation.

The role assignment was set to:

- Assignment type: Eligible
- Scope: Tenant

Governance controls were enabled including:

- MFA requirement for activation
- Justification requirement
- Time-bound activation window
- Optional ticket information requirement

📸 Evidence:

![Image 2-13-26 at 23 06](https://github.com/user-attachments/assets/5bb173d2-d1a2-4a37-9620-acde199cb0c5)

![Image 2-13-26 at 23 08](https://github.com/user-attachments/assets/fdd6e0ee-8810-4a2f-ab53-8a3c4571ceeb)

![Image 2-13-26 at 23 10](https://github.com/user-attachments/assets/1bd7f22b-a317-45e5-87ed-afb47368e4a5)

---

## ⚡ Just-In-Time Role Activation

The test identity signed in and activated the Global Administrator role using Privileged Identity Management.

Activation required:

- Multi-factor authentication
- Justification entry

After activation, the role appeared under active assignments with a defined expiration window.

📸 Evidence:

![Image 2-13-26 at 23 11](https://github.com/user-attachments/assets/19d3f558-3cc8-42d4-afa8-a531a8528acc)

![Image 2-13-26 at 23 12](https://github.com/user-attachments/assets/2604119a-7ef5-4fbf-9a04-abcb554205f4)

![Image 2-13-26 at 23 13](https://github.com/user-attachments/assets/7ba28341-ac31-4050-a8ef-b0db50bd57b5)

![Image 2-13-26 at 23 15](https://github.com/user-attachments/assets/867f9d89-54d9-430f-9f5f-ed1db73d74a4)

![Image 2-13-26 at 23 15](https://github.com/user-attachments/assets/c3c5214f-c003-4a50-9243-e915e905b9a9)

![Image 2-13-26 at 23 16](https://github.com/user-attachments/assets/cf9e421d-8e95-4514-b70b-c5440b248944)

---

## ⏱️ Early Privilege Removal (Least Privilege Simulation)

To simulate real operational behavior where administrators elevate only briefly, the role was manually deactivated approximately five minutes after activation.

This demonstrates:

- Avoiding unnecessary privilege duration
- Reducing attack surface
- Following least privilege principles

After deactivation:

- The role was no longer active
- The identity returned to non-privileged state

📸 Evidence:

![Image 2-13-26 at 23 19](https://github.com/user-attachments/assets/b772f64c-6932-460b-a0a3-95229f183056)

![Image 2-13-26 at 23 22](https://github.com/user-attachments/assets/d57ac5d3-de52-40f6-97b0-ceda6ff4da09)

---

## 🔎 Audit Validation

Role lifecycle activity was validated using audit data.

### Privileged Identity Management Audit History

Audit history confirmed:

- Role activation event
- Role deactivation event
- User identity
- Timestamp

📸 Evidence:

![Image 2-13-26 at 23 24](https://github.com/user-attachments/assets/970fc828-ff94-4046-8d3b-389f028686c1)

---

### Microsoft Entra Audit Logs

Audit logs provided tenant-wide confirmation of privileged role changes, including activation and removal.

📸 Evidence:

![Image 2-13-26 at 23 25](https://github.com/user-attachments/assets/29bfdd1c-2de9-4484-92ca-9822339cd61b)

---

## 🧠 Key Takeaways

- Privileged access should never be permanent when avoidable.
- Just-in-time elevation reduces risk exposure.
- Manual deactivation reinforces least privilege practices.
- PIM provides full visibility into privileged activity.
- Audit logs support security investigations and compliance reviews.

---

## ✅ Final Outcome

A privileged access governance model was successfully implemented where:

- Administrative access required activation
- Elevation was protected by MFA and justification
- Privilege was removed shortly after use
- All activity was captured in audit records

This project reflects real-world enterprise practices for managing 
