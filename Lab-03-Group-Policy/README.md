
---

# 📁 Group Policy (GPO) Lab

```md
# Group Policy Objects (GPO) Lab

## Overview
This lab focuses on implementing and testing Group Policy Objects in a Windows Server Active Directory environment. The goal is to simulate enterprise-level policy enforcement and endpoint configuration management.

This project demonstrates:
- Group Policy creation and management
- Security policy enforcement
- Drive mapping via GPO
- Desktop environment configuration
- Client-side policy troubleshooting

---

## Environment
- Windows Server 2022 (Domain Controller)
- Windows 10/11 Domain-Joined Client
- Active Directory Domain: corp.local

---

## Group Policy Implementations

### 1. Password Policy
- Configured minimum password length
- Enforced password complexity requirements
- Set password expiration policy

Applied via:
- Default Domain Policy

---

### 2. Drive Mapping Policy
- Configured network drive mappings using Group Policy Preferences
- Mapped shared drive based on user group membership

Example:
- HR → H: drive mapped to \\Server\HRShare
- IT → I: drive mapped to \\Server\ITShare

---

### 3. Desktop Wallpaper Policy
- Applied a centralized desktop wallpaper to all domain users
- Used Group Policy Preferences to enforce consistency across endpoints

---

### 4. Security Policy (Service Control)
- Disabled specific Windows services using Group Policy
- Demonstrated endpoint hardening techniques

---

## Testing & Validation

### Policy Updates
- Used `gpupdate /force` on client machines
- Verified policy application using:
```cmd
gpresult /r
