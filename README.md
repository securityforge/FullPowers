# FullPowers
FullPowers is a Windows privilege escalation research tool that allows a standard user to regain full administrative privileges (SeDebugPrivilege, SeLoadDriverPrivilege, SeTakeOwnershipPrivilege, etc.) in situations where the user is part of the Administrators group but is running without elevated token privileges due to UAC or filtered tokens.

📌 Overview

On Windows, even if a user belongs to the Administrators group, the resulting logon session might still run with a filtered token lacking powerful privileges (due to UAC).

FullPowers leverages token duplication techniques to create a new process with a full administrative token, restoring high-privilege rights typically stripped by UAC.

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
