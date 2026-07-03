# Action1 Endpoint Management Practice

This project documents my personal lab practice with Action1 endpoint management. The goal is to show hands-on learning with endpoint inventory, remote management, patch management concepts, software deployment concepts, and endpoint monitoring in a controlled lab environment.

This was completed as personal lab work for learning and portfolio purposes. It does not represent paid production endpoint administration experience.

## Lab Purpose

The purpose of this lab is to practice using an endpoint management platform in a small IT support-style environment. I used Action1 to explore how endpoints can be inventoried, monitored, remotely managed, and prepared for patching or software deployment workflows.

This page is intentionally a summary. Exact policies, reports, deployment results, and screenshots will be added only when they are documented and safe to publish.

## Tools Used

- Action1 endpoint management platform
- Windows lab virtual machines
- Oracle VirtualBox lab networking
- Windows Server 2022 domain controller from the Active Directory lab
- Windows 11 lab client virtual machines
- Internet access through NAT adapters for cloud connectivity

Details still to document:

- Action1 tenant or console configuration: To be documented
- Endpoint agent installation steps: To be documented
- Exact endpoint list used for testing: To be documented

## Environment Overview

This Action1 practice was connected to my broader VirtualBox Active Directory lab.

Documented environment details:

- Windows Server 2022 domain controller used in the lab
- Windows 11 lab client virtual machines
- Private host-only network for Active Directory communication
- Separate NAT adapter added for internet access and Action1 cloud connectivity

The lab was designed to keep Active Directory communication on a private network while still allowing managed endpoints to reach Action1 over the internet.

## What I Practiced

- Reviewing endpoint inventory information in Action1
- Practicing remote device management concepts
- Exploring patch management workflows and terminology
- Reviewing software deployment concepts
- Monitoring endpoint visibility and connection status
- Thinking through how endpoint management tools support help desk and desktop support work
- Troubleshooting network access needed for cloud-based endpoint management

I did not document specific production policies, real company devices, or real user data in this lab.

## Skills Demonstrated

- Endpoint inventory awareness
- Remote management concepts
- Patch management fundamentals
- Software deployment planning concepts
- Endpoint monitoring and connection-status review
- VirtualBox networking troubleshooting
- Understanding the difference between isolated lab networks and internet-connected management tools
- Help desk-style documentation and troubleshooting notes
- Safe public documentation habits, including avoiding secrets and real user data

## Troubleshooting Notes

| Issue | What I Checked | Resolution | Status |
| --- | --- | --- | --- |
| Action1 could not communicate with all VMs while the lab used only an isolated host-only network | Reviewed the VirtualBox network design and confirmed the VMs needed internet access for Action1 while still keeping private lab communication | Added a second NAT adapter to the VMs so they could stay connected to the isolated Active Directory lab network while also reaching the internet for Action1 | Resolved in lab |

Lessons learned:

- Cloud-based endpoint management tools need reliable internet connectivity from managed devices.
- An isolated host-only network is useful for private lab communication, but it does not provide internet access by itself.
- Using a second NAT adapter can preserve the private lab network while allowing cloud management connectivity.
- Network design should be documented before troubleshooting endpoint visibility issues.

Additional troubleshooting areas to document later:

- Agent installation issues: To be documented
- Endpoint check-in delays: To be documented
- Patch scan or deployment errors: To be documented
- Remote management connection issues: To be documented

## Screenshot Plan

Screenshots will be added later after they are reviewed and redacted.

Planned screenshots:

- Action1 dashboard or endpoint overview, with sensitive details removed
- Endpoint inventory view
- Example device details page
- Patch management view or scan result summary
- Software deployment concept screen, if safely documentable
- Endpoint monitoring or connection-status view
- VirtualBox network adapter configuration showing host-only and NAT separation

Screenshots must be reviewed before publishing so no secrets, tokens, private account details, device identifiers, or personal information are exposed.

## Planned Documentation

- Action1 setup overview
- Endpoint agent installation steps
- Endpoint inventory notes
- Patch management workflow notes
- Software deployment concept notes
- Remote management practice notes
- Endpoint monitoring notes
- Screenshot captions and redaction checklist

## Future Improvements

- Add redacted screenshots from the Action1 lab
- Document the endpoint onboarding process step by step
- Add a short table of lab endpoints, using safe generic names if needed
- Document one patch management practice workflow after it is verified
- Document one software deployment practice workflow after it is verified
- Add more troubleshooting examples as they are encountered
- Connect Action1 practice notes back to common help desk workflows such as device inventory, patch follow-up, and remote support
