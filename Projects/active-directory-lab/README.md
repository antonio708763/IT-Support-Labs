# VirtualBox Active Directory Lab

This project documents my personal Active Directory and help desk practice lab built with Windows Server 2022 and Windows 11 virtual machines in Oracle VirtualBox. The goal is to practice common IT support and junior system administration tasks in a safe private lab environment.

## Status

This documentation is still in progress. The main lab design, virtual machines, domain controller details, network layout, and several practice areas are documented, but screenshots and some step-by-step procedures still need to be added.

This is personal lab work for learning and portfolio purposes. It is not production enterprise administration experience.

## Lab Purpose

The purpose of this lab is to build hands-on familiarity with Active Directory and Windows domain support concepts. In this lab, I configured and documented a Windows Server 2022 domain controller, practiced joining Windows 11 clients to the domain, reviewed user and group management, configured basic password and account lockout policy settings, practiced file sharing, and worked through troubleshooting scenarios.

## Tools Used

- Windows host running Oracle VirtualBox
- Windows Server 2022 Standard Evaluation
- Windows 11 client virtual machines
- Ubuntu Lab 1 virtual machine, not configured yet
- Active Directory Domain Services
- DNS
- File sharing/SMB
- Group Policy Management
- Remote Desktop practice
- Action1 endpoint management practice

## Lab Environment

| Component | Details |
| --- | --- |
| Host machine | Windows host running Oracle VirtualBox |
| Virtualization platform | Oracle VirtualBox |
| Domain controller VM | `TX-DC-01`, Windows Server 2022 Standard Evaluation |
| Client VM 1 | Windows 11 Lab client VM |
| Client VM 2 | Windows 11 Lab 2 client VM |
| Additional VM | Ubuntu Lab 1 exists but is not configured yet |
| Lab domain | `Project.org`, used only inside the private lab |
| Host-only lab network | `10.1.10.0/24` |
| Domain controller lab IP | `10.1.10.10/24` |
| Domain controller DNS setting | Points to `127.0.0.1` on the domain controller |

## VM Resources

| VM | CPU | Memory | Virtual Disk |
| --- | --- | --- | --- |
| Server 2022 domain controller | 2 CPUs | 4 GB RAM | 35 GB |
| Windows 11 Lab client | 2 CPUs | 4 GB RAM | 45 GB |
| Windows 11 Lab 2 client | 2 CPUs | 4 GB RAM | 45 GB |
| Ubuntu Lab 1 | To be documented | To be documented | To be documented |

## Network Design

- **Adapter 1:** Host-only Adapter for isolated Active Directory and domain communication.
- **Adapter 2:** NAT adapter for internet access and cloud tool connectivity.
- **Host-only network:** `10.1.10.0/24`.
- **NAT network:** Provides internet access separately from the isolated Active Directory lab network.

This two-adapter design lets the Windows lab machines communicate with the domain controller on the private lab network while still allowing internet access for tools such as Action1.

## Server Roles and Services

Configured in the lab:

- Active Directory Domain Services
- DNS
- File sharing/SMB
- Some Remote Desktop practice

Not confirmed yet:

- DHCP has not been fully documented or confirmed as configured.

## Active Directory Practice

Documented so far:

- Domain controller hostname: `TX-DC-01`
- Lab domain: `Project.org`
- Created users: John Doe, Kevin, and Terry
- Created security group: IT Support
- Current user location: default Users container
- Custom Organizational Units: not documented yet

## File Sharing Practice

- Created an SMB share named `IT Support`.
- Share path: `\\TX-DC-01\IT Support`.
- The IT Support security group description references folder access to `\\TX-DC-01\IT Support`.

## Group Policy Practice

I reviewed and configured password and account lockout policy settings in the Default Domain Policy.

| Policy Area | Setting Practiced |
| --- | --- |
| Password history | 24 passwords remembered |
| Maximum password age | 90 days |
| Minimum password age | 1 day |
| Minimum password length | 12 characters |
| Password complexity | Enabled |
| Account lockout threshold | 3 invalid logon attempts |
| Account lockout duration | 360 minutes |
| Reset account lockout counter | 30 minutes |

## What I Practiced

- Configuring Windows Server 2022 in a VirtualBox lab
- Promoting a Server 2022 VM for Active Directory Domain Services practice
- Practicing DNS concepts for a domain environment
- Joining Windows 11 virtual machines to a private lab domain
- Creating and reviewing user accounts
- Creating and reviewing a security group
- Reviewing default Active Directory containers
- Configuring basic password and account lockout policy settings
- Creating an SMB share for file access practice
- Practicing Remote Desktop basics
- Troubleshooting lab networking for domain and cloud management access
- Documenting setup notes in an employer-facing portfolio format

## Skills Demonstrated

- Active Directory fundamentals
- Windows Server administration practice
- Windows 11 client support practice
- Domain joining and account authentication concepts
- User and group management
- Basic Group Policy understanding
- DNS troubleshooting concepts
- File sharing and permissions awareness
- VirtualBox networking with host-only and NAT adapters
- Help desk-style documentation and problem solving
- Security-minded documentation habits for a public portfolio

## Troubleshooting Notes

| Issue | What I Checked | Resolution | Status |
| --- | --- | --- | --- |
| Windows 11 client could not join the domain | Checked that the client could reach the network, then reviewed the client DNS settings | Updated the Windows 11 client DNS setting so it pointed to the domain controller instead of an external DNS server | Resolved in lab |
| Action1 could not communicate with all VMs while the lab used only an offline host-only network | Reviewed the VirtualBox network design and confirmed the VMs needed both private lab communication and internet access | Added a second NAT adapter to each VM so the machines could stay connected to the isolated AD lab network while also reaching the internet for Action1 | Resolved in lab |

Possible troubleshooting areas to document next:

- Additional domain join failures
- DNS lookup issues
- DHCP or static IP configuration mistakes
- User login problems
- Group Policy settings not applying
- Shared folder or permission access issues

## Screenshot Plan

Screenshots will be added later to show the lab setup and key configuration areas. Screenshots must be reviewed and redacted before publishing so no sensitive details, private account information, tokens, or unnecessary system identifiers are exposed.

Planned screenshots:

- VirtualBox VM list and basic VM settings
- Domain controller system information
- Active Directory Users and Computers showing documented lab users and groups
- Group Policy password and account lockout settings
- SMB share configuration for `\\TX-DC-01\IT Support`
- Windows 11 client domain membership
- Network adapter configuration showing host-only and NAT separation

## Planned Documentation

- Step-by-step domain controller setup notes
- Windows 11 domain join steps
- DNS configuration notes
- More detail on the file share and group access testing
- Remote Desktop practice notes
- Action1 endpoint management notes
- Custom Organizational Unit plan, if added later
- DHCP notes, if configured and confirmed later

## Future Improvements

- Add redacted screenshots of the lab setup
- Add a simple network diagram
- Document exact steps used to configure Active Directory Domain Services
- Document exact steps used to join each Windows 11 client to the domain
- Add examples of user, group, and future Organizational Unit structure
- Document Group Policy testing results
- Add more troubleshooting examples as they are encountered
