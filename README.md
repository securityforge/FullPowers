# FullPowers
FullPowers is a Windows privilege escalation research tool that allows a standard user to regain full administrative privileges (SeDebugPrivilege, SeLoadDriverPrivilege, SeTakeOwnershipPrivilege, etc.) in situations where the user is part of the Administrators group but is running without elevated token privileges due to UAC or filtered tokens.

📌 Overview

On Windows, even if a user belongs to the Administrators group, the resulting logon session might still run with a filtered token lacking powerful privileges (due to UAC).

FullPowers leverages token duplication techniques to create a new process with a full administrative token, restoring high-privilege rights typically stripped by UAC.

**Usage:
C:\wamp\www>FullPowers.exe
FullPowers.exe
[+] Started dummy thread with id 3848
[+] Successfully created scheduled task.
[+] Got new token! Privilege count: 7
[+] CreateProcessAsUser() OK
Microsoft Windows [Version 10.0.17763.2300]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\Windows\system32>whoami /priv
whoami /priv**

PRIVILEGES INFORMATION
----------------------

Privilege Name                Description                               State  
============================= ========================================= =======
SeAssignPrimaryTokenPrivilege Replace a process level token             Enabled
SeIncreaseQuotaPrivilege      Adjust memory quotas for a process        Enabled
SeAuditPrivilege              Generate security audits                  Enabled
SeChangeNotifyPrivilege       Bypass traverse checking                  Enabled
SeImpersonatePrivilege        Impersonate a client after authentication Enabled
SeCreateGlobalPrivilege       Create global objects                     Enabled
SeIncreaseWorkingSetPrivilege Increase a process working set            Enabled

What it provides

A restored token with all admin privileges enabled

Ability to execute processes with full administrator rights

Useful during post-exploitation when UAC limits your token

🛠️ Features

Restores missing admin privileges

Bypasses filtered admin tokens (UAC restrictions)

Spawns a fully privileged process or command

Minimal, single executable

Works on multiple Windows versions

⚠️ Disclaimer

This project is intended strictly for:

Security research

Educational study

Authorized penetration testing

Any unauthorized use is illegal and the author assumes no responsibility for misuse or damage.
