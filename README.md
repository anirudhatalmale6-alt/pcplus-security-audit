# PC Plus Computing - USB Toolkit

Two portable PowerShell tools for PC technicians. Run from USB, no installation required.

## 1. Hardware & Security Audit (PCPlus-SecurityAudit.ps1)

Comprehensive hardware diagnostic + 15-point security audit with branded PDF report.

### Features
- **15-Point Security Audit**: Antivirus, firewall, BitLocker, patches, password policy, admin accounts, Secure Boot, TPM, RDP, SMBv1, UAC, guest account, auto-login, AV definitions
- **Full Hardware Diagnostics**: RAM slots/speed/manufacturer, GPU/VRAM, motherboard/BIOS, battery health/cycle count, disk SMART (power-on hours, wear, temperature, read errors), monitors, printers, audio devices, USB devices, Device Manager errors, Windows license status, temperatures
- **0-100 Security Score** with letter grades (A through F)
- **Professional Branded PDF** with PC Plus Computing branding, cover page, executive summary
- **Windows Forms UI**: Customer name, contact name, technician name, output folder
- **Date and time** on cover page and footer

### Usage
```powershell
# Right-click > Run with PowerShell, or:
Set-ExecutionPolicy Bypass -Scope Process -Force
.\PCPlus-SecurityAudit.ps1
```

### Output
Reports saved to `PCPlus-Audits/` folder:
`CustomerName - HOSTNAME - Hardware Security Audit 2026-05-19.pdf`

---

## 2. Windows Debloat & Lockdown (PCPlus-Debloat.ps1)

Strips bloatware from Windows 10/11. Designed for office PCs that only need browsing and printing.

### Options (checkboxes, pick what you need)
- Remove bloatware apps (Cortana, Xbox, Solitaire, TikTok, Netflix, etc.)
- Disable Windows telemetry & data collection
- Disable Cortana, Widgets, Game Bar
- Remove OneDrive
- Clean Start Menu and taskbar
- Disable web search in Start Menu
- Prevent Windows from reinstalling removed apps
- Disable Windows suggestions, tips, and ads
- Disable unnecessary services (keeps Print Spooler)
- Create daily Downloads folder cleanup task (deletes files older than 1 day)
- Block non-admin software installs (UAC enforcement)
- Disable Microsoft Store
- Optimize power settings (high performance, no sleep)

### Usage
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
.\PCPlus-Debloat.ps1
```

Creates a detailed log file next to the script.

---

## Requirements
- Windows 10 or Windows 11
- PowerShell 5.1+ (built into Windows)
- Administrator privileges
- Edge or Chrome for PDF generation (audit tool)

## USB Setup
Copy both .ps1 files to a USB drive. Insert into client PC, right-click the script you need, "Run with PowerShell".
