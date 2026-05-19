# PC Plus Computing - Portable Security Audit Tool

Standalone PowerShell script that performs a comprehensive security and system audit on Windows 10/11 PCs, generating a branded PDF report. Runs from a USB drive with no installation required.

## Features

- **15-Point Security Audit**: Windows Update, antivirus, firewall, BitLocker, password policy, admin accounts, network shares, startup programs, RDP status, SMBv1, PowerShell policy, DNS config, open ports, disk health, system info
- **Scoring System**: 0-100 security score with letter grades (A+ through F)
- **Branded PDF Reports**: Professional reports with PC Plus Computing branding
- **Windows Forms UI**: Launch dialog for customer/contact/technician info, progress bar, completion summary
- **Zero Installation**: Runs directly from USB or any folder
- **Auto-Elevation**: Prompts for admin rights if needed

## Requirements

- Windows 10 or Windows 11
- PowerShell 5.1+ (built into Windows 10/11)
- Administrator privileges
- Microsoft Edge or Google Chrome (for PDF generation; falls back to HTML if neither available)

## Usage

### From USB Drive
1. Copy `PCPlus-SecurityAudit.ps1` to a USB drive
2. Insert USB into target PC
3. Right-click the script > **Run with PowerShell**
4. Fill in customer name, contact name, and technician name
5. Click **Run Audit**
6. Reports are saved to a `PCPlus-Audits` folder next to the script

### Quick Launch (PowerShell)
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
.\PCPlus-SecurityAudit.ps1
```

## Output

Reports are saved to `PCPlus-Audits/` in the same directory as the script:
- `CustomerName_HOSTNAME_2026-05-19.pdf` (primary)
- `CustomerName_HOSTNAME_2026-05-19.html` (fallback if no browser for PDF)

## Security Checks

| # | Check | What It Tests |
|---|-------|--------------|
| 1 | Windows Update | Pending updates and last install date |
| 2 | Antivirus | Real-time protection status |
| 3 | Firewall | All profile states (Domain/Private/Public) |
| 4 | BitLocker | Drive encryption status |
| 5 | Password Policy | Complexity, length, expiry settings |
| 6 | Admin Accounts | Number of local admin accounts |
| 7 | Network Shares | Non-default shares exposed |
| 8 | Startup Programs | Excessive auto-start entries |
| 9 | RDP Status | Remote Desktop enabled/disabled |
| 10 | SMBv1 | Legacy protocol check |
| 11 | PowerShell Policy | Execution policy setting |
| 12 | DNS Configuration | DNS server analysis |
| 13 | Open Ports | Listening network connections |
| 14 | Disk Health | SMART status and space |
| 15 | System Info | OS version, uptime, specs |
