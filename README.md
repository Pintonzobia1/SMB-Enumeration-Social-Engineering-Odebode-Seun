Penetration Testing Guides: SMB Enumeration and Social Engineering
Overview
This repository contains educational guides on penetration testing techniques, focusing on SMB enumeration and social engineering via website cloning. These documents are for learning purposes in controlled environments, such as labs with Metasploitable 2 VMs. Always adhere to ethical guidelines and legal restrictions.

SMB_Enumeration.pdf: A cheat sheet for enumerating Windows/Samba hosts using tools like enum4linux and smbclient.
Social-Engineering.pdf: A tutorial on using the Social-Engineer Toolkit (SET) for credential harvesting through site cloning.

Contents

SMB Enumeration
Social Engineering
Requirements
Usage
Disclaimer

SMB Enumeration
This guide demonstrates SMB reconnaissance on a Metasploitable 2 VM (IP 172.17.0.2):

Scan for open ports (139/445) with nmap.
Use enum4linux for:
User lists (-U, e.g., root, www-data with RIDs).
Machine lists (-M).
Share lists (-S, e.g., print$, tmp, opt, IPC$, ADMIN$).
Password policies (-P, min length, lockout).
Groups (-G).
Aggressive enumeration (-A).

smbclient for anonymous share access, listing, and file uploads.
Highlights vulnerabilities: anonymous tmp access, symlink traversal, CVE-2007-2447 in Samba 3.0.20-3.0.25.

Screenshots show terminal outputs and RID cycling.
Social Engineering
This tutorial covers website cloning for phishing with SET:

Launch setoolkit and select Website Attack Vectors > Credential Harvester > Site Cloner.
Set attacker IP (e.g., 10.6.6.1) and clone target URL (e.g., DVWA login).
Create meta-refresh HTML redirect.
Capture credentials in XML reports (/root/.set/reports/).
Victim redirection to original site.

Includes menu navigation, terminal commands, and browser screenshots for simulations.
Requirements

Kali Linux or similar pentesting distro.
Tools: nmap, enum4linux, smbclient, setoolkit.
Target: Metasploitable 2 VM.

Usage

Clone the repo: git clone <repo-url>.
Review PDFs for step-by-step instructions.
Practice in a lab environment only.

Disclaimer
This content is for educational use. Do not use for unauthorized activities. The author is not responsible for misuse.
