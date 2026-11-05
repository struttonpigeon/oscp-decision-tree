# OSCP Decision Tree

An interactive, single-file decision tree for the OSCP exam. Click through decisions based on your current scenario (AD vs Standalone, OS, access level) to reach step-by-step methodology with copy-paste commands.

The idea is you have a guide during your exam when you are fatigued and suffering. The exam now includes AV-enabled Windows boxes, and this tree covers the bypass techniques you need.

Ideally you also go and download my OSCP toolkit and windows exploit suggester. Hope it helps.


<img width="941" height="662" alt="image" src="https://github.com/user-attachments/assets/4715708f-359d-4888-8c0c-6e93e811882c" />


## Usage

1. Download `index.html`
2. Open it in any browser
3. Click through the decision tree based on your exam scenario

No server, no dependencies, no internet required. This works fully offline during the exam.

### Features

- Copy buttons on every code block
- Interactive port search filter (type a port number to filter the routing table)
- Breadcrumb navigation with back button

## What's Inside

### Decision Paths
- **Standalone Machines:** Windows / Linux x No Access / Low Priv / Admin-Root
- **AD Set:** Initial Access -> MS01 Low Priv -> MS01 Admin -> MS02 -> Domain Controller

### Exam Guardrails
Explicit rules documented in the tree: no SQLmap, no Nessus, no AI, no LLMNR/NBT-NS/MDNS poisoning, Responder as passive SMB listener only, Metasploit on max 1 target, msfvenom + multi/handler everywhere else.

### Initial Access (Windows & Linux)
- Workspace setup, nmap scanning (TCP full + UDP), fingerprinting
- Port-to-action routing table with interactive search filter
- 20-minute panic guide (structured decision tree for when you're stuck)
- Web enumeration (feroxbuster depth 4, ffuf vhosts, SQLi, LFI, PHP wrappers, file upload, command injection, .git exposure)
- SMB/MSSQL/SNMP enumeration
- Default credentials table (20+ services)
- Reverse shells (Penelope OSCP-safe handler, PowerShell, msfvenom non-Meterpreter)
- File transfer methods (certutil, iwr, SMB)
- Credential validation across services (nxc, evil-winrm, xfreerdp)
- CGI/Shellshock, Tomcat Manager, Jenkins Script Console
- Redis unauthenticated SSH key write
- Rsync share enumeration
- Restricted shell escape techniques

### Windows Privilege Escalation (9 Steps)
- Shell stabilization and first-commands checklist
- AV evasion: AMSI bypass (two methods with dynamic field filtering), CLM detection, simple AV tricks (rename, relocate, in-memory), decision flow, Donut shellcode wrapping (-x 2, -z 2, -e 3)
- WinPEAS panic-reading order (9 priorities)
- Windows Exploit Suggester (115+ CVEs, AlwaysInstallElevated, unquoted paths, writable services, UAC state, token privileges)
- SeImpersonatePrivilege (GodPotato, PrintSpoofer, JuicyPotato, SigmaPotato, FullPowers.exe)
- Other abusable privileges (SeBackup, SeRestore, SeDebug, SeTakeOwnership)
- Service binary hijack (XAMPP/Apache), unquoted paths, writable PATH hijack, SharpUp
- Stored credentials (cmdkey/runas, PowerShell history, registry, AlwaysInstallElevated, McAfee SiteList.xml, IIS web.config, DPAPI, KeePass cracking, WiFi passwords)
- SSH key handling on Windows (find keys, copy to Kali, chmod/ssh-i, dos2unix, passphrase cracking, lateral movement via known_hosts)
- DLL hijack, scheduled task hijacking, RunasCs, UAC bypass
- Node.js debugger exploitation (port 9229)
- Automated enumeration (PrivescCheck, PowerUp) and proof capture

### Linux Privilege Escalation (6 Steps)
- LinPEAS panic-reading order (12 priorities)
- sudo -l and GTFOBins
- SUID/SGID, PATH hijack, capabilities
- Cron jobs, pspy, wildcard attacks
- Credential hunting (SSH key handling with multi-key search, known_hosts lateral movement, persistence key generation, dos2unix, KeePass cracking, writable /etc/passwd, shadow cracking)
- Docker/LXD container breakout, NFS no_root_squash, LD_PRELOAD, disk group/debugfs, writable systemd services, MySQL/PostgreSQL running as root
- Kernel exploits (last resort)

### Active Directory Attack Chain
- BloodHound (neo4j + SharpHound collector) setup and enumeration
- Kerberoasting, AS-REP Roasting
- ACL abuse (WriteDACL -> Domain Admins -> DCSync chain via bloodyAD)
- ADCS certificate abuse (ESC1, ESC4, ESC8 via certipy-ad)
- Resource-Based Constrained Delegation (RBCD)
- Lateral movement (PSExec, WinRM, DCOM, overpass-the-hash, pass-the-ticket)
- NTDS.dit extraction (DCSync + shadow copy alternative)
- Golden/Silver tickets
- Ligolo-ng pivoting (modern + legacy syntax, double pivoting, listener forwarding)
- bloodyAD quick reference for AD object manipulation

### Post-Exploitation
- Credential harvesting (mimikatz full sweep, SAM dump, LSA secrets)
- Proof capture reminders with search commands

### Step 0 — OSCP Toolkit
The root page includes a Step 0 that tells you to clone the [OSCPToolkit](https://github.com/struttonpigeon/OSCPToolkit) and set up BloodHound (neo4j + SharpHound) before the exam.

## Referenced Repositories

- [struttonpigeon/OSCPToolkit](https://github.com/struttonpigeon/OSCPToolkit)
- [struttonpigeon/Linux-Exploitation](https://github.com/struttonpigeon/Linux-Exploitation)
- [struttonpigeon/Windows-Exploitation](https://github.com/struttonpigeon/Windows-Exploitation)
- [struttonpigeon/AD-Exploitation](https://github.com/struttonpigeon/AD-Exploitation)
- [struttonpigeon/OSCP_Notes](https://github.com/struttonpigeon/OSCP_Notes)
- [struttonpigeon/Win-Exploit-Suggester](https://github.com/struttonpigeon/Win-Exploit-Suggester)
- [Kiosec/Linux-Exploitation](https://github.com/Kiosec/Linux-Exploitation)
- [Tib3rius/Cheatsheets](https://github.com/Tib3rius/Cheatsheets)
- [brightio/penelope](https://github.com/brightio/penelope)
- [CravateRouge/bloodyAD](https://github.com/CravateRouge/bloodyAD)

## License

MIT
