# OHTS
CVE-2017-8759 | .NET Framework Remote Code Execution Vulnerability

1)	Introduction

A remote code execution vulnerability exists when Microsoft .NET Framework processes untrusted input. An attacker who successfully exploited this vulnerability in software using the .NET framework could take control of an affected system. An attacker could then install programs; view, change, or delete data; or create new accounts with full user rights. Users whose accounts are configured to have fewer user rights on the system could be less impacted than users who operate with administrative user rights.
To exploit the vulnerability, an attacker would first need to convince the user to open a malicious document or application. The security update addresses the vulnerability by correcting how .NET validates untrusted input. Microsoft .NET Framework allow an attacker to execute code remotely via a malicious document or application, .NET Framework Remote Code Execution Vulnerability.

2)	Vulnerable Versions

According to Microsoft, the following are the affected products
•	Microsoft .NET Framework 2.0 SP2
•	Microsoft .NET Framework 3.5
•	Microsoft .NET Framework 3.5.1
•	Microsoft .NET Framework 4.5.2
•	Microsoft .NET Framework 4.6
•	Microsoft .NET Framework 4.6.1
•	Microsoft .NET Framework 4.6.2
•	Microsoft .NET Framework 4.7

3)	Attack Process

The attack occurs in the following manner:
•	Create Rtf file, with the help of Python script or manually.
•	When the user opens the document, winword.exe issues a HTTP request to a remote server to retrieve a malicious HTA file.
•	The HTA file returned by the server with an embedded malicious script.
•	exe looks up the file handler for application/hta through a DLLobject, which causes the Microsoft HTA application (mshta.exe) to load and execute the malicious script.

4)	Requirements

First, we need two virtual machines. I am using Kali Linux as my exploitation environment and Windows7 as my victim. 

Then, we need to have a small research on the CVE-2017-8759 for get some idea about the vulnerability.

•	https://github.com/bhdresh/CVE-2017-8759 
•	https://github.com/nccgroup/CVE-2017-8759 
•	https://securitytracker.com/id/1039324 
•	https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2017-8759 
•	https://www.securityfocus.com/bid/100742 
•	https://www.exploit-db.com/exploits/42711
•	https://www.cvedetails.com/cve/CVE-2017-8759/

I used above references to get more details about this .NET Framework Remote Code Execution Vulnerability. As in the Figure 4.3 this vulnerability has 9.3 CVSS score and also there is total information disclosure, resulting in all system files being revealed, total compromise of system integrity, there is a complete loss of system protection, resulting in the entire system being compromised, total shutdown of the affected resource. The attacker can render the resource completely unavailable. The access conditions are somewhat specialized. Some preconditions must be satistified to exploit. Authentication is not required to exploit the vulnerability.

