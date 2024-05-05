<p align="center">
<img src="https://place-hold.it/600x200" alt="Place Holder Image"/>
<!-- <img src="assets/logo.svg" alt="Logo Text There" /> -->
</p>

# Windows Server 2003 to 2012 Domain Migration
Transitioned an existing domain infrastructure from Windows Server 2003 to Windows Server 2012.

## Environments and Technologies Used

- Microsoft Exchange Server 2010
- Microsoft Exchange Server 2012
- Microsoft Hyper-V Server 2012
- Item 3

## Operating Systems Used

- Windows Server 2003
- Windows Server 2010
- Windows Server 2012

## High-Level Deployment and Configuration Steps

- Data Collection – Gathered the following statistics and attributes from the Windows Server 2003 Domain Controller and Exchange Server: Mailbox Storage Quotas, Key Delegates, Public Folders, Misc. Mailboxes, PST file usage, Public Folder usage, Email Routing Topology, Distribution Groups, Client Software Versions, Mail Integrated Applications and Devices, Public Names, and SSL Certificates
- Windows Server 2012 Hyper-V Installation – Verified server hardware configuration. Prepared Windows Server 2012 Installation media. Installed Windows Server 2012. Activated Windows, Performed & Configured Windows Updates, Configured Computer Name, Configured Static IP Address, Configured DNS, Time zone settings, Added Hyper-V role. Configured Hyper-V
- Domain Preparation – Elevated existing Forest Functional Level to Windows Server 2003 (was running at Windows 2000) Completed Forest and Domain Preparation
- Windows Server 2012 Domain Controller Installation – Added Active Directory Domain Services role to Primary Domain Controller, Added DHCP role to the Primary Domain Controller. Confirmed replication of all user and computer accounts. Removed Windows Server 2003 domain controller as Global Catalog server. Added Active Directory Domain Services role to Secondary Domain Controller, Added DHCP role to Secondary Domain Controller, configured DHCP failover between Primary and Secondary Domain controller. Made Windows Server 2003 domain controller the tertiary option in the DHCP scope server options. Confirmed users were able to successfully authenticate using the new domain controllers. Confirmed users were receiving DHCP leases from the new DHCP servers. Confirmed users were able to perform name resolution using the new DNS servers
- Exchange Server 2010 Installation & Migration – Since Microsoft does not support moving directly from Exchange Server to 2003 to Exchange Server 2013 an intermediate migration needed to be performed to Exchange Server 2010. The following was performed: Installed Exchange Server 2010 with the Mailbox, Client Access, Hub Transport, and Unified Messaging Role; Applied Active Directory Schema update for Exchange; Applied Exchange Service Packs; Configured Hub Transport Send, Receive & Relay connectors; Moved all user mailboxes to the temporary Exchange Server; Moved all public folders to the temporary Exchange Server; configured temporary SSL certificate, tested inbound/outbound mail flow internally and externally; Manually uninstalled Exchange Server 2003 due to Control Panels failure to remove the software; Corrected corrupt Active Directory entries from removed Server 2003 installation; retested mail flow
- Windows Server 2003 Domain Controller Demotion – Demoted Windows Server 2003 Domain Controller. Removed DNS & DHCP roles. Promoted Domain and Forest functional level to Windows Server 2012
- Exchange Server 2013 Installation & Migration –Installed Exchange Server 2013 with the Mailbox & Client Access Role; Applied Active Directory Schema update for Exchange; Configured Mail Flow Send, Receive & Relay connectors; Moved all user mailboxes to the Exchange Server; Configured GoDaddy SAN SSL certificate, tested inbound/outbound mail flow internally and externally; Uninstalled Exchange Server 2010. Retested mail flow.
- Installed and Configured Anti-Spam Email Gateway
- Backup – Added Windows Server Backup Role to the Hypervisor & Exchange Server. Configured the backup schedules. Updated NAS device firmware. Initiated backup.

<h2>Architecture Diagram</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
