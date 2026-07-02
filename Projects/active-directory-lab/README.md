# VirtualBox Active Directory Lab

This project documents my personal Active Directory lab built with Windows Server 2022 and Windows 11 virtual machines in VirtualBox. The goal is to practice common IT support and junior system administration tasks in a safe lab environment.

## Status

This documentation is still in progress. The main lab goals and practice areas are listed, but some setup details, screenshots, network notes, and step-by-step procedures still need to be documented.

I will continue updating this page as I build, test, troubleshoot, and organize the lab. Any unknown details are marked as "To be documented" instead of being guessed.

## Lab Purpose

The purpose of this lab is to build hands-on familiarity with Active Directory and Windows domain support concepts. This includes setting up a Windows Server environment, joining a Windows 11 client to a domain, managing users and groups, practicing basic Group Policy, and documenting troubleshooting steps.

This is personal lab work for learning and portfolio purposes. It is not production enterprise administration experience.

## Tools Used

- VirtualBox
- Windows Server 2022
- Windows 11
- Active Directory Domain Services
- DNS and DHCP concepts
- Group Policy Management
- Windows administrative tools

## Lab Environment

- **Host machine:** To be documented
- **Virtualization platform:** VirtualBox
- **Server VM:** Windows Server 2022
- **Client VM:** Windows 11
- **Domain name:** To be documented
- **Network configuration:** To be documented
- **Server roles configured:** To be documented

## What I Practiced

- Installing and configuring Windows Server 2022 in a virtual lab
- Practicing Active Directory Domain Services concepts
- Creating and organizing user accounts
- Creating and managing security groups
- Joining a Windows 11 virtual machine to a domain
- Practicing basic Group Policy settings
- Reviewing DNS and DHCP concepts in a domain environment
- Creating or planning shared resources for user access practice
- Documenting setup steps and troubleshooting notes

## Skills Demonstrated

- Active Directory fundamentals
- Windows Server administration practice
- Windows 11 client support practice
- Domain joining and account authentication concepts
- User and group management
- Basic Group Policy understanding
- DNS and DHCP troubleshooting concepts
- Shared resource and permissions awareness
- Help desk-style documentation and problem solving

## Troubleshooting Notes

Use this section to document issues found during the lab and how they were resolved.

| Issue | What I Checked | Resolution | Status |
| --- | --- | --- | --- |
| Windows 11 client could not join the domain | Checked that the client could reach the network, then reviewed the client DNS settings | Updated the Windows 11 client DNS setting so it pointed to the domain controller instead of an external DNS server | Resolved in lab |

Possible troubleshooting areas to document next:

- Additional domain join failures
- DNS lookup issues
- DHCP or static IP configuration mistakes
- User login problems
- Group Policy settings not applying
- Shared folder or permission access issues

## Planned Documentation

- Lab network diagram
- Server and client VM specifications
- Domain controller setup notes
- Domain join steps for the Windows 11 client
- User, group, and organizational unit examples
- Group Policy settings tested in the lab
- Shared resource and permissions examples
- Screenshots with sensitive details removed

## Future Improvements

- Add screenshots of the lab setup with any sensitive details removed
- Document the exact VM specifications and network settings
- Add a simple network diagram
- Add step-by-step notes for domain controller setup
- Add examples of user, group, and organizational unit structure
- Document Group Policy settings tested in the lab
- Add more troubleshooting examples as they are encountered
