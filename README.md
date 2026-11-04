# OSCP Decision Tree

An interactive, single-file decision tree for the OSCP exam. Click through decisions based on your current scenario (AD vs Standalone, OS, access level) to reach step-by-step methodology with copy-paste commands.

The idea is you have a guide during your exam when you are fatigued and suffering.

Ideally you also go and download my OSCP toolkit and windows exploit suggester. Hope it helps.

## Usage

1. Download `index.html`
2. Open it in any browser
3. Click through the decision tree based on your exam scenario

No server, no dependencies, no internet required. This works fully offline during the exam.

## What's Inside

### Decision Paths
- **Standalone Machines:** Windows / Linux × No Access / Low Priv / Admin-Root
- **AD Set:** Initial Access → MS01 Low Priv → MS01 Admin → MS02 → Domain Controller

### Methodology Covers
- Workspace setup, nmap scanning, port-to-action routing
- Web enumeration (feroxbuster, ffuf, SQLi, LFI, file upload, command injection)
- Default credentials table (20+ services)
- Windows privesc (WinPEAS reading order, Potato attacks, service hijack, stored creds, DLL hijack, registry, McAfee SiteList)
- Linux privesc (LinPEAS reading order, sudo/GTFOBins, SUID PATH hijack, capabilities, cron/wildcard, Docker/LXD, NFS, LD_PRELOAD)
- AD attack chain (BloodHound CE, Kerberoasting, AS-REP, ACL abuse, ADCS ESC1/4/8, RBCD, delegation, DCSync, Golden/Silver tickets)
- Ligolo-ng pivoting (modern + legacy syntax)
- bloodyAD quick reference for AD object manipulation
- Reverse shells, file transfer, shell stabilization
- Post-exploitation credential harvesting
- Proof capture reminders

### Step 0 — OSCP Toolkit
The root page includes a Step 0 that tells you to clone the [OSCPToolkit](https://github.com/struttonpigeon/OSCPToolkit) and set up BloodHound CE before the exam.

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
