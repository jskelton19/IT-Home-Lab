# Active Directory Home Lab (Windows Server 2022)

## Overview
This project simulates a small enterprise Active Directory environment using Windows Server 2022. The goal was to gain hands-on experience with core Windows Server and identity management tasks commonly used in Tier 1 / Tier 2 IT support environments.

This lab focuses on:
- Active Directory Domain Services (AD DS)
- User and Group Management
- Organizational Unit (OU) design
- Group Policy implementation
- PowerShell automation
- Basic enterprise identity administration

---

## Environment
- Windows Server 2022 (Domain Controller)
- Windows 10/11 Client VM
- VirtualBox / VMware Workstation
- Domain: corp.local

---

## Lab Setup

### Domain Configuration
- Installed Active Directory Domain Services (AD DS)
- Promoted server to Domain Controller
- Created new forest: corp.local
- Configured DNS on the Domain Controller

---

### Organizational Units (OUs)
Created a simplified enterprise structure:

- HR
- Sales
- Workstations

This structure was used to simulate department-based access control and policy application.

---

## User & Group Management

### User Creation
- Created users manually in Active Directory Users and Computers (ADUC)
- Created users using PowerShell to simulate onboarding workflows

### PowerShell Example:
```powershell
Import-Csv "users.csv" | ForEach-Object {
    New-ADUser -Name $_.Name `
    -GivenName $_.FirstName `
    -Surname $_.LastName `
    -SamAccountName $_.Username `
    -UserPrincipalName $_.UPN `
    -Path $_.OU `
    -AccountPassword (ConvertTo-SecureString "Password123!" -AsPlainText -Force) `
    -Enabled $true
}
```
## Group Management

- Created security groups for HR and Sales
- Assigned users to groups based on department role
- Implemented group-based access control for testing file share permissions

## Client Domain Join Testing**
- Joined Windows 10/11 VM to domain successfully
- Verified authentication using HR and Sales user accounts
- Tested login behavior across different OUs

## Troubleshooting Scenarios
1. DNS Misconfiguration

Issue: Client machines could not join domain
Fix: Verified DNS pointed to Domain Controller IP address

2. Domain Join Failure

Issue: Workstation failed to join domain
Fix: Corrected DNS settings and verified network connectivity

3. Group Policy Not Applying

Issue: GPO did not apply to client machine
Fix: Used gpupdate /force and verified correct OU placement

## Evidence

- ADUC screenshots (users, groups, OUs)
- PowerShell scripts
- Domain join validation
- Skills Demonstrated
- Active Directory administration
- Windows Server setup and configuration
- User and group management
- PowerShell automation
- Basic enterprise troubleshooting

